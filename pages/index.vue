<template>
  <main class="flex-auto">
    <div class="max-w-7xl mx-auto h-full py-6 sm:px-6 lg:px-8 flex justify-center">
      <GameCardsStack
        :cards="visibleCards"
        @cardAccepted="handleCardAccepted"
        @cardRejected="handleCardRejected"
        @cardSkipped="handleCardSkipped"
        @hideCard="removeCardFromDeck"
      />
    </div>
  </main>
</template>

<script>
export default {
  data () {
    return {
      visibleCards: ['Test', 'Vue.js', 'Webpack', 'Test']
    }
  },
  methods: {
    handleCardAccepted () {
      console.log('handleCardAccepted')
    },
    handleCardRejected () {
      console.log('handleCardRejected')
    },
    handleCardSkipped () {
      console.log('handleCardSkipped')
    },
    removeCardFromDeck () {
      this.visibleCards.shift()
    }
  }
}
</script>
