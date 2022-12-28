<template>
  <div class="container">
    <PlayerPanel v-for="(dataContent, playerName) in debtData" :playerName="playerName" :dataContent="dataContent" />
  </div>
</template>

<script>
  import PlayerPanel from "./PlayerPanel.vue"

  export default {
    name: "Board",
    props: {
      debtData: Object
    },
    components: {
      PlayerPanel
    }
  }

</script>
