<template>
  <li class="nav-item">
    <a class="nav-link" href="#" @click="toggleAssist">
      プレイ補助
      <span class="badge bg-primary" v-if="assist">オン</span>
      <span class="badge bg-secondary" v-else>オフ</span>
    </a>
  </li>
</template>

<script>
export default {
  name: "ToggleAssist",
  emits: [
    "toggle-assist"
  ],
  data() {
    return {
      assist: true
    }
  },
  methods: {
    toggleAssist() {
      this.assist = !this.assist
      this.$emit("toggle-assist", this.assist)
    }
  }
}
</script>
