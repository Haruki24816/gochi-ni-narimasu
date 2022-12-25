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
          <li class="nav-item">
            <a class="nav-link" href="#">プレイ補助 <span class="badge bg-primary" v-if="true">オン</span><span class="badge bg-secondary" v-else>オフ</span></a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              サウンド変更
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
              <li><a class="dropdown-item active" href="#">借金①</a></li>
              <li><a class="dropdown-item" href="#">借金②</a></li>
              <li><a class="dropdown-item" href="#">借金③</a></li>
              <li><a class="dropdown-item" href="#">大破産</a></li>
              <li><a class="dropdown-item" href="#">レジスター</a></li>
              <li><a class="dropdown-item" href="#">爆発</a></li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">リセット</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">記録シートDL</a>
          </li>
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
export default {
  name: "Navbar"
}
</script>
