<template>
  <div id="Topic">
    <Nuxt-link to="/">
      ><img id="backToWorld" src="/assets/Icon_Return_SVG.svg" alt="s"
    /></Nuxt-link>
    <Lottie :path="topic.activist_portrait"></Lottie>
    <div id="topicdetails">
      <h1 class="activistName">{{ topic.activist }}</h1>
      <h2>{{ topic.name }}</h2>
      <h2>{{ topic.location[0].name }}</h2>
      <p>{{ topic.description }}</p>
      <div id="container-medialinks">
        <a :href="url + topic.video"
          ><img class="media" src="/assets/Icon_Eye.svg" alt="s" />
        </a>
        <a :href="url + topic.podcast"
          ><img class="media" src="/assets/Icon_Megaphone.svg" alt="s" />
        </a>
        <a :href="url + topic.material"
          ><img class="media" src="/assets/Icon_Texts.svg" alt="s"
        /></a>
      </div>
    </div>
  </div>
</template>

<script>
import Lottie from "../../components/Lottie.vue";
export default {
  components: {
    Lottie,
  },
  data() {
    return {
      url: "https://sblicke.uber.space/assets/",
    };
  },
  async asyncData({ route }) {
    const topic = await fetch(
      "https://sblicke.uber.space/items/topic/" + route.params.id
    )
      .then((res) => res.json())
      .then((res) => res.data);
    return { topic };
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
@font-face {
  font-family: HandsOfMumu;
  src: url("/assets/fonts/HandsOfMumu.ttf");
}
.activistName {
  font-family: HandsOfMumu;
}
#Topic {
  background: #e3743c;
  width: 100vw;
  height: 100vh;
  display: flex;
}
#topicdetails {
  width: 50vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
#container-medialinks {
  display: flex;
  justify-content: space-between;
  place-items: center;
}
.media {
  margin: 5vw;
  width: 5vw;
}
#backToWorld {
  width: 5vw;
  margin: 1vw;
}
</style>
