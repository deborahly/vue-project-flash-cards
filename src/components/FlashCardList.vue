<template>
  <div>
    <h1>Flashcards</h1>
    <FlashCard
      v-for="card in cards"
      :key="card.term"
      :term="card.term"
      :definition="card.definition"
      :list="true"
    />
    <br />
    <hr />
    <FlashCardForm @createCard="addCard" />
  </div>
</template>

<script>
import FlashCard from './FlashCard.vue'
import FlashCardForm from './FlashCardForm.vue'
export default {
  props: {
    cards: { type: Array, required: true }
  },
  components: {
    FlashCard,
    FlashCardForm
  },
  methods: {
    addCard(card) {
      // eslint-disable-next-line vue/no-mutating-props
      this.cards.push(card)
    }
  }
}
</script>
