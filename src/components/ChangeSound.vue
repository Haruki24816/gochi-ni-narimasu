<template>
  <li class="nav-item">
    <a class="nav-link" href="#" data-bs-toggle="modal" data-bs-target="#exampleModal">サウンド変更</a>
  </li>
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">サウンド変更</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div class="list-group">
            <button type="button" v-for="soundName in soundList" :class="listClass(soundName)"
              @click="$emit('change-sound', soundName)">{{ soundName }} </button>
          </div>
        </div>
      </div>
    </div>
  </div>
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
        return "list-group-item list-group-item-action active"
      } else {
        return "list-group-item list-group-item-action"
      }
    }
  },
  emits: [
    "change-sound"
  ]
}
</script>
