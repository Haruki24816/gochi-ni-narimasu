<template>
  <div class="d-flex">
    <input class="form-control me-2" type="text" placeholder="プレイヤー名" aria-label="プレイヤー名" v-model="playerName" @keydown.enter="emitPlayerName">
    <button class="btn btn-outline-success flex-shrink-0" v-if="validate" @click="emitPlayerName">追加</button>
    <button class="btn btn-outline-success flex-shrink-0 disabled" v-else>追加</button>
  </div>
</template>

<script>
  export default {
    name: "AddPlayer",
    props: {
      playerList: Array
    },
    methods: {
      emitPlayerName() {
        if (this.validate == false) {
          return
        }
        this.$emit("add-player-name", this.playerName)
        this.playerName = ""
      }
    },
    computed: {
      validate() {
        if (this.playerName == "") {
          return false
        } else if (this.playerList.includes(this.playerName)) {
          return false
        } else {
          return true
        }
      }
    },
    data() {
      return {
        playerName: ""
      }
    }
  }

</script>
