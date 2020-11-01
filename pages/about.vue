<template>
  <div>
    <h1>About Dad Jokes</h1>
    <p>This is a page that displays dad jokes.</p>
    <p>Created with <a href="https://nuxtjs.org/">Nuxt.js</a> by <a href="https://github.com/mnegabriel">Gabriel Dantas</a> </p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About Dad Jokes",
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
