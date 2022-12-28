<template>
  <Navbar>
    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
      <ToggleAssist />
      <ChangeSound />
      <Reset />
      <li class="nav-item"><a class="nav-link" href="./sheet.pdf">記録シートDL</a></li>
    </ul>
    <AddPlayer :playerList="Object.keys(debtData)" @add-player-name="addPlayerName" />
  </Navbar>
  <Board :playerList="Object.keys(debtData)" />
</template>

<script>
  import Navbar from "./components/Navbar.vue"
  import Board from "./components/Board.vue"
  import ToggleAssist from "./components/ToggleAssist.vue"
  import ChangeSound from "./components/ChangeSound.vue"
  import Reset from "./components/Reset.vue"
  import AddPlayer from "./components/AddPlayer.vue"

  export default {
    name: "App",
    components: {
      Navbar,
      Board,
      ToggleAssist,
      ChangeSound,
      Reset,
      AddPlayer
    },
    data() {
      return {
        debtData: {}
      }
    },
    methods: {
      addPlayerName(playerName) {
        let others = Object.keys(this.debtData)
        this.debtData[playerName] = {}
        for (let num in others) {
          let otherPlayerName = others[num]
          this.debtData[playerName][otherPlayerName] = 0
          this.debtData[otherPlayerName][playerName] = 0
        }
        console.log(this.debtData)
      }
    }
  }

</script>
