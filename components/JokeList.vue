<template>
  <ul class="jokelist">
    <li
      v-for="joke of jokes"
      :key='joke.id'
    >
    <nuxt-link :to="'jokes/'+ joke.id">
      <p>{{joke.joke}}</p>
    </nuxt-link>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'JokeList',
  props: [ 'jokes' ]
}
</script>

<style>
.jokelist p {
  margin: 1rem 0;
  padding: 1rem 2rem;
  border: 1px solid #ccc;
}
</style>
