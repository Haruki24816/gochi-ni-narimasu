<template>
  <div class="container">
    <PlayerPanel v-for="playerName in playerList" :playerName="playerName" :playerList="playerList" />
  </div>
</template>

<script>
  import PlayerPanel from "./PlayerPanel.vue"

  export default {
    name: "Board",
    props: {
      playerList: Array
    },
    components: {
      PlayerPanel
    }
  }

</script>
