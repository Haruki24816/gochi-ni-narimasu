<template>
  <hr>
  <h4>{{ playerName }}</h4>
  <div class="d-flex justify-content-center flex-wrap">
    <div class="m-2 lh-sm" style="width:120px" v-for="(amount, opponentPlayer) in dataContent">
      <div class="text-truncate" style="font-size:small">
        {{ opponentPlayer }}<br>
        <strong style="font-size:large">{{ (amount).toLocaleString("ja-JP") }}</strong> 円
      </div>
      <div class="btn-group btn-group-lg w-100 mt-1" role="group" aria-label="input">
        <button type="button" :class="buttonClass(amount)"
          @click="$emit('increase-debt', [playerName, opponentPlayer])">＋</button>
        <button type="button" :class="buttonClass(amount)"
          @click="$emit('decrease-debt', [playerName, opponentPlayer])">－</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PlayerPanel",
  props: {
    playerName: String,
    dataContent: Object,
    assist: Boolean
  },
  emits: [
    "increase-debt",
    "decrease-debt"
  ],
  methods: {
    buttonClass(amount) {
      if (!this.assist) {
        return "btn btn-primary"
      } else if (amount > 0) {
        return "btn btn-success"
      } else if (amount < 0) {
        return "btn btn-danger"
      } else {
        return "btn btn-primary"
      }
    }
  }
}

</script>
