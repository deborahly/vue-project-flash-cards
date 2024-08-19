<template>
  <main>
    <button @click="switchComponent">{{ buttonText }}</button>
    <div class="wrapper">
      <FlashCardList v-if="list" :cards="cards" />
      <FlashCardScroller v-else :cards="cards"/>
    </div>
  </main>
</template>

<script>
import FlashCardList from './components/FlashCardList.vue'
import FlashCardScroller from './components/FlashCardScroller.vue'
export default {
  data() {
    return {
      list: true,
      buttonText: 'Switch to scroller',
      cards: [
        { term: 'H2O', definition: 'water' },
        { term: 'NaCl', definition: 'salt' }
      ]
    }
  },
  components: {
    FlashCardList,
    FlashCardScroller
  },
  methods: {
    switchComponent() {
      this.list = !this.list
      if (this.list) {
        this.buttonText = 'Switch to scroller'
      } else {
        this.buttonText = 'Switch to list'
      }
    }
  }
}
</script>

<style scoped>
main {
  left: 0;
  line-height: 1.5;
  display: flex;
  flex-direction: column;
}
</style>
