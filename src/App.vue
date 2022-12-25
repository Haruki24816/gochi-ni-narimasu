<template>
  <Navbar>
    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
      <ToggleAssist />
      <ChangeSound />
      <Reset />
      <li class="nav-item"><a class="nav-link" href="/sheet.pdf">記録シートDL</a></li>
    </ul>
    <form class="d-flex">
      <input class="form-control me-2" type="text" placeholder="プレイヤー名" aria-label="プレイヤー名">
      <button class="btn btn-outline-success flex-shrink-0">追加</button>
    </form>
  </Navbar>
  <Board />
</template>

<script>
import Navbar from "./components/Navbar.vue"
import Board from "./components/Board.vue"
import ToggleAssist from "./components/ToggleAssist.vue"
import ChangeSound from "./components/ChangeSound.vue"
import Reset from "./components/Reset.vue"

export default {
  name: "App",
  components: {
    Navbar,
    Board,
    ToggleAssist,
    ChangeSound,
    Reset
  }
}
</script>
