<template>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
      リセット
    </a>
    <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
      <li><a :class="menuAmountClass" href="#" @click="$emit('reset-amount')">金額のみリセットする</a></li>
      <li><a :class="menuAllClass" href="#" @click="$emit('reset-all')">すべてリセットする</a></li>
    </ul>
  </li>
</template>

<script>
export default {
  name: "Reset",
  emits: [
    "reset-amount",
    "reset-all"
  ],
  props: {
    debtData: Object
  },
  computed: {
    menuAllClass() {
      if (Object.keys(this.debtData).length == 0) {
        return "dropdown-item disabled"
      } else {
        return "dropdown-item"
      }
    },
    menuAmountClass() {
      let num = 0
      for (let firstPerson in this.debtData) {
        let innerData = this.debtData[firstPerson]
        for (let secondPerson in innerData) {
          let amount = innerData[secondPerson]
          num += Math.abs(amount)
        }
      }
      if (num == 0) {
        return "dropdown-item disabled"
      } else {
        return "dropdown-item"
      }
    }
  }
}
</script>
