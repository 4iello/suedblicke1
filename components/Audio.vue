<template>
  <audio id="Audio" :src="audiourl"></audio>
</template>

<script>
export default {
  props: {
    audioUrl: {
      type: String,
      default: '',
    },
  },
}
</script>

<style>
#Audio {
  height: 100vh;
  width: 100vw;
}
</style>
