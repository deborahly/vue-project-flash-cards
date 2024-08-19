<template>
  <form v-on:submit.prevent="createCard(term, definition)" action="#" method="post">
    <input v-model="term" type="text" name="term" placeholder="Term" />
    <input v-model="definition" type="text" name="definition" placeholder="Definition" />
    <button type="submit" name="button">Add Card</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      term: '',
      definition: ''
    }
  },
  methods: {
    createCard(term, definition) {
      this.$emit('createCard', { term, definition })
      this.term = ''
      this.definition = ''
    }
  }
}
</script>
