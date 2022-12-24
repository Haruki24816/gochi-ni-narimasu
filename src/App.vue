<template>
  <NavMenu/>
  <Board/>
</template>

<script>
import NavMenu from "./components/NavMenu.vue"
import Board from "./components/Board.vue"

export default {
  name: "App",
  components: {
    NavMenu,
    Board
  }
}
</script>
