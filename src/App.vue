<template>
  <Navbar/>
  <Board/>
</template>

<script>
import Navbar from "./components/Navbar.vue"
import Board from "./components/Board.vue"

export default {
  name: "App",
  components: {
    Navbar,
    Board
  }
}
</script>
