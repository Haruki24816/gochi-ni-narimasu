<template>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown"
      aria-expanded="false">
      サウンド変更
    </a>
    <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
      <li v-for="soundName in soundList">
        <a :class="listClass(soundName)" href="#" @click="$emit('change-sound', soundName)">{{ soundName }}</a>
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  name: "ChangeSound",
  props: {
    currentSoundName: String,
    soundList: Array
  },
  methods: {
    listClass(name) {
      if (name == this.currentSoundName) {
        return "dropdown-item active"
      } else {
        return "dropdown-item"
      }
    }
  },
  emits: [
    "change-sound"
  ]
}
</script>
