<template>
  <div class="container text-center">
    <PlayerPanel v-for="(dataContent, playerName) in debtData" :assist="assist" :playerName="playerName"
      :dataContent="dataContent" @increase-debt="$emit('increase-debt', $event)"
      @decrease-debt="$emit('decrease-debt', $event)" />
    <hr v-if="num != 0">
    <div class="alert alert-primary m-3" role="alert" v-if="num < 2">
      プレイヤーを2人以上追加してください
    </div>
  </div>
</template>

<script>
import PlayerPanel from "./PlayerPanel.vue"

export default {
  name: "Board",
  props: {
    debtData: Object,
    assist: Boolean
  },
  components: {
    PlayerPanel
  },
  computed: {
    num() {
      if (typeof this.debtData != "object") {
        return 0
      } else {
        return Object.keys(this.debtData).length
      }
    }
  },
  emits: [
    "increase-debt",
    "decrease-debt"
  ]
}

</script>
