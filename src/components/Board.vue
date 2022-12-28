<template>
  <div class="container">
    <PlayerPanel v-for="(dataContent, playerName) in debtData" :playerName="playerName" :dataContent="dataContent" @increase-debt="$emit('increase-debt', $event)" @decrease-debt="$emit('decrease-debt', $event)" />
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
