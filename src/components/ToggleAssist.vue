<template>
  <li class="nav-item">
    <a class="nav-link" href="#">プレイ補助 <span class="badge bg-primary" v-if="true">オン</span><span class="badge bg-secondary" v-else>オフ</span></a>
  </li>
</template>

<script>
export default {
  name: "ToggleAssist"
}
</script>
