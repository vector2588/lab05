<template>
  <div id="flashMessageEdit" v-if="GStore.flashMessageEdit">
    {{ GStore.flashMessageEdit }}
  </div>
  <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
  <p>{{ event.description }}</p>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore']
}
</script>

<style>
@keyframes yellowfade {
  from {
    background: yellow;
  }
  to {
    background: transparent;
  }
}

#flashMessageEdit {
  animation-name: yellowfade;
  animation-duration: 3s;
}
</style>
