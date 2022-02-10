<template>
  <div id="container"></div>
</template>

<script>
import lottie from 'lottie-web'

export default {
  props: {
    path: String,
  },
  mounted() {
    const asset = this.path
    const url = 'https://sblicke.uber.space/assets/'
    const path = url + asset
    console.log(path)
    // eslint-disable-next-line prefer-const
    let animation = lottie.loadAnimation({
      container: document.getElementById('container'),
      renderer: 'svg',
      loop: false,
      path,
    })

    console.log(animation)
  },
}
</script>

<style>
#container {
  width: 50vw;
  height: 100vh;
}
</style>
