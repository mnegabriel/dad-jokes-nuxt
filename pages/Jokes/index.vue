<template>
  <div>
    <SearchJoke @search-term='jokeSearch'/>

    <JokeList :jokes='jokes' />
  </div>
</template>

<script>
import axios from 'axios'

import JokeList from '@/components/JokeList'
import SearchJoke from '@/components/SearchJoke'

export default {
  data() {
    return {
      jokes: [],
      jokesUrl : 'https://icanhazdadjoke.com/search',
      config: {
        headers: {
          'Accept': 'application/json'
        }
      }
    }
  },

  components: {
    JokeList,
    SearchJoke
  },

  async created() {
    try {
      const res = await axios(this.jokesUrl, this.config)

      this.jokes = res.data.results
    } catch (error) {
      console.log(error)
    }
  },

  methods: {
    async jokeSearch(text) {
      try {
        const jokeSearchUrl = `${this.jokesUrl}?term=${text}`
        const res = await axios(jokeSearchUrl, this.config)

        this.jokes = res.data.results
      } catch (error) {
        console.log(error)
      }
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

