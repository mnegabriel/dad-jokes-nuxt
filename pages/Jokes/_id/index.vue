<template>
  <div>
    <nuxt-link to='/jokes'>Back to jokes</nuxt-link>

    <h2> {{joke}} </h2>
    <hr>

    <small> Joke ID: {{$route.params.id}} </small>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      joke: '',
      id: this.$route.params.id,
      jokesUrl : 'https://icanhazdadjoke.com/j/',
      config: {
        headers: {
          'Accept': 'application/json'
        }
      }
    }
  },

  async created() {
    try {
      const searchUrl = this.jokesUrl + this.id
      console.log(searchUrl)
      const res = await axios(searchUrl, this.config)
      console.log(res)

      this.joke = res.data.joke
    } catch (error) {
      console.log(error)
    }
  },

  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best site for worst dad jokes'
        }
      ]
    }
  }
}
</script>
