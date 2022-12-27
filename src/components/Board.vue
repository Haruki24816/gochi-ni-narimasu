<template>
  <div class="container">
    <PlayerPanel v-for="playerName in players" :playerName="playerName" :players="players" />
  </div>
</template>

<script>
  import PlayerPanel from "./PlayerPanel.vue"

  export default {
    name: "Board",
    props: {
      players: Array
    },
    components: {
      PlayerPanel
    }
  }

</script>
