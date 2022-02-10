<template>
  <div id="Worldmap">
    <WorldMap :eyeAnimationFinished="eyeAnimationFinished" :topics="topics" />
  </div>
</template>

<script>
import WorldMap from "~/components/WorldMap.vue";
export default {
  components: { WorldMap },
  async asyncData() {
    const topics = await fetch("https://sblicke.uber.space/items/topic").then(
      (res) => res.json()
    );
    return { topics };
  },
  data() {
    return {
      eyeAnimationFinished: false,
    };
  },
  mounted() {
    setTimeout(() => (this.eyeAnimationFinished = true), 5000);
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
#Worldmap {
}
</style>
