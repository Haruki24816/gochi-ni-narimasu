<template>
  <div class="alert alert-primary mt-3" role="alert">
    <h4>{{ playerName }}</h4>
    <ul class="mb-0">
      <li v-for="opponentPlayer in players">
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
      players: Array
    }
  }

</script>
