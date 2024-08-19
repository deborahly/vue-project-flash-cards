<template>
  <div v-if="list" class="box list">
    <div>Term: {{ term }}</div>
    <div>Definition: {{ definition }}</div>
  </div>
  <div v-else class="box scroller">
    <div>{{ currentSide }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSide: this.term
    }
  },
  props: {
    term: { type: String, required: true },
    definition: { type: String, required: true },
    list: { type: Boolean, required: false, default: true }
  },
  methods: {
    flip() {
      this.currentSide = this.currentSide === this.definition ? this.term : this.definition
    }
  }
}
</script>

<style scoped>
.box {
  margin: 0 auto 0.5rem 0;
  padding: 2rem 1rem 2rem 1rem;
  max-width: 50%;
  border-style: solid;
  border-width: 1px;
  border-color: black;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
