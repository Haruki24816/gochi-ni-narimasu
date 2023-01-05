<template>
  <li class="nav-item">
    <a class="nav-link" href="#" data-bs-toggle="modal" data-bs-target="#exampleModal">リセット</a>
  </li>
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">リセット</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div class="d-grid gap-2">
            <button class="btn btn-primary" type="button" @click="$emit('reset-amount')"
              data-bs-dismiss="modal">金額のみリセットする</button>
            <button class="btn btn-primary" type="button" @click="$emit('reset-all')"
              data-bs-dismiss="modal">すべてリセットする</button>
          </div>
        </div>
      </div>
    </div>
  </div>
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
