<template>
  <div class="container">
    <AppHeader />
    <Nuxt />
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader'

export default {
  components: {
    AppHeader
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background-color: #f4fafa;
}

a {
  color: #666;
  text-decoration: none;
}

ul {
  list-style: none;
}

.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background-color: #fff;
}
</style>
