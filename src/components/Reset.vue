<template>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown"
      aria-expanded="false">
      リセット
    </a>
    <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
      <li><a class="dropdown-item" href="#" @click="$emit('reset-amount')">金額のみリセットする</a></li>
      <li><a class="dropdown-item" href="#" @click="$emit('reset-all')">すべてリセットする</a></li>
    </ul>
  </li>
</template>

<script>
export default {
  name: "Reset",
  emits: [
    "reset-amount",
    "reset-all"
  ]
}
</script>
