<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <span class="navbar-brand">
        <img src="../assets/logo.png" alt="" width="30" class="d-inline-block align-text-top me-2">
        KING 借金記録
      </span>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <ToggleAssist/>
          <ChangeSound/>
          <Reset/>
          <li class="nav-item"><a class="nav-link" href="/sheet.pdf">記録シートDL</a></li>
        </ul>
        <form class="d-flex">
          <input class="form-control me-2" type="text" placeholder="プレイヤー名" aria-label="プレイヤー名">
          <button class="btn btn-outline-success flex-shrink-0">追加</button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
import ToggleAssist from "./ToggleAssist.vue"
import ChangeSound from "./ChangeSound.vue"
import Reset from "./Reset.vue"

export default {
  name: "Navbar",
  components: {
    ToggleAssist,
    ChangeSound,
    Reset
  }
}
</script>
