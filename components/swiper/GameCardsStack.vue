<template>
  <div class="cards">
    <GameCard
      v-for="(card, index) in cards"
      :key="card"
      :card="card"
      :is-current="index === 0"
      @cardAccepted="$emit('cardAccepted');"
      @cardRejected="$emit('cardRejected');"
      @cardSkipped="$emit('cardSkipped');"
      @hideCard="$emit('hideCard');"
    />
  </div>
</template>

<script>
export default {
  props: {
    cards: {
      type: Array,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.cards {
  position: relative;
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: 50px;
  width: 500px;
  max-width: 100%;
}
</style>
