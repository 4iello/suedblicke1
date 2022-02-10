<template>
  <video id="Video" :src="videourl"></video>
</template>

<script>
export default {
  props: {
    videoUrl: {
      type: String,
      default: '',
    },
  },
}
</script>

<style>
#Video {
  height: 100vh;
  width: 100vw;
}
</style>
