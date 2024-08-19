<template>
  <div>
    <h1>Flashcards</h1>
    <FlashCard
      ref="flashcard"
      :key="card.term"
      :term="card.term"
      :definition="card.definition"
      :list="false"
    />
    <br />
    <hr />
    <button @click="prevCard">Previous Card</button>
    <button @click="$refs.flashcard.flip">Flip Card</button>
    <button @click="nextCard">Next Card</button>
  </div>
</template>

<script>
import FlashCard from './FlashCard.vue'
export default {
  data() {
    return {
      card: this.cards[0],
      index: 0
    }
  },
  props: {
    cards: { type: Array, required: true }
  },
  components: {
    FlashCard
  },
  methods: {
    prevCard() {
      if (this.index != 0) {
        this.index--
        this.card = this.cards[this.index]
      } else {
        alert('This is the initial card.')
      }
    },
    nextCard() {
      if (this.index != this.cards.length - 1) {
        this.index++
        this.card = this.cards[this.index]
      } else {
        alert('This is the final card.')
      }
    }
  }
}
</script>
