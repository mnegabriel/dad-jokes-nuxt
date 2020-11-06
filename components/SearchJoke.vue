<template>
  <form @submit.prevent="handleSubmit">
    <input
      type="text"
      v-model="text"
      placeholder="Search joke..."
    >
    <input type="submit" value="Search Jokes">
  </form>

</template>

<script>
export default {
  name: 'SearchJoke',
  data() {
    return {
      text:''
    }
  },
  methods: {
    handleSubmit() {
      this.$emit('search-term', this.text)
      this.text = ''
    }
  }
}
</script>

<style >

</style>
