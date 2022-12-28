<template>
  <div class="alert alert-primary mt-3" role="alert">
    <h4>{{ playerName }}</h4>
    <ul class="mb-0">
      <li v-for="(amount, opponentPlayer) in dataContent">
        {{ opponentPlayer }}: {{ (amount).toLocaleString("ja-JP") }}円
        <br>
        <button type="button" class="btn btn-primary" @click="$emit('increase-debt', [playerName,opponentPlayer])">＋</button>
        <button type="button" class="btn btn-primary" @click="$emit('decrease-debt', [playerName,opponentPlayer])">－</button>
      </li>
    </ul>
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
