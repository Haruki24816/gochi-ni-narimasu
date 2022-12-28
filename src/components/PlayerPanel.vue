<template>
  <div class="alert alert-primary mt-3" role="alert">
    <h4>{{ playerName }}</h4>
    <ul class="mb-0">
      <li v-for="opponentPlayer in playerList">
        {{ opponentPlayer }}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "PlayerPanel",
    props: {
      playerName: String,
      playerList: Array
    }
  }

</script>
