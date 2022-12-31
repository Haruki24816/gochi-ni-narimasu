<template>
  <h4>{{ playerName }}</h4>
  <div class="row">
    <div class="col" v-for="(amount, opponentPlayer) in dataContent">
      <div>
        {{ opponentPlayer }}<br>
        {{ (amount).toLocaleString("ja-JP") }} 円
      </div>
      <div class="btn-group btn-group-lg" role="group" aria-label="input">
        <button type="button" class="btn btn-primary"
          @click="$emit('increase-debt', [playerName, opponentPlayer])">＋</button>
        <button type="button" class="btn btn-primary"
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
    dataContent: Object
  }
}

</script>
