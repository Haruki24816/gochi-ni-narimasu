<template>
  <Navbar>
    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
      <ToggleAssist @toggle-assist="assist = $event" />
      <ChangeSound :currentSoundName="currentSoundName" :soundList="Object.keys(sounds)"
        @change-sound="changeSound($event)" />
      <Reset @reset-all="resetAll" @reset-amount="resetAmount" :debtData="debtData" />
      <li class="nav-item"><a class="nav-link" href="./sheet.pdf">記録シートDL</a></li>
    </ul>
    <AddPlayer :playerList="Object.keys(debtData)" @add-player-name="addPlayerName" />
  </Navbar>
  <Board :assist="assist" :debtData="debtData" @increase-debt="increaseDebt($event[0], $event[1])"
    @decrease-debt="decreaseDebt($event[0], $event[1])" />
</template>

<script>
import Navbar from "./components/Navbar.vue"
import Board from "./components/Board.vue"
import ToggleAssist from "./components/ToggleAssist.vue"
import ChangeSound from "./components/ChangeSound.vue"
import Reset from "./components/Reset.vue"
import AddPlayer from "./components/AddPlayer.vue"
const audioFiles = import.meta.glob("./assets/sounds/*.mp3")

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
      debtData: {},
      assist: true,
      sounds: {
        "無音": null,
        "ランダム": null
      },
      currentSoundName: "レジスター"
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
    },
    increaseDebt(firstPerson, secondPerson) {
      this.debtData[firstPerson][secondPerson] += 500
      this.debtData[secondPerson][firstPerson] -= 500
      this.playSound()
    },
    decreaseDebt(firstPerson, secondPerson) {
      this.debtData[firstPerson][secondPerson] -= 500
      this.debtData[secondPerson][firstPerson] += 500
      this.playSound()
    },
    playSound() {
      if (this.currentSoundName == "無音") {
        return
      } else if (this.currentSoundName == "ランダム") {
        let soundList = Object.keys(this.sounds).slice(2)
        let name = soundList[Math.floor(Math.random() * soundList.length)]
        let audio = this.sounds[name]
        audio.currentTime = 0
        audio.play()
      } else {
        let audio = this.sounds[this.currentSoundName]
        audio.currentTime = 0
        audio.play()
      }
    },
    changeSound(name) {
      this.currentSoundName = name
      this.playSound()
    },
    resetAmount() {
      let playerList = Object.keys(this.debtData)
      this.resetAll()
      for (let num in playerList) {
        this.addPlayerName(playerList[num])
      }
    },
    resetAll() {
      this.debtData = {}
    }
  },
  created() {
    for (let path in audioFiles) {
      audioFiles[path]().then((file) => {
        let url = file.default
        let name = url.split("/").slice(-1)[0].slice(0, -4)
        name = name.split("-")[0]
        this.sounds[name] = new Audio(url)
      })
    }
  }
}

</script>
