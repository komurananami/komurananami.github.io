<template>
  <div class="container">
    <img alt="shape-top" src="../assets/blob.svg" class="shape-top" />
    <img alt="shape-green" src="../assets/blob.svg" class="shape-bottom" />
    <div class="home">
      <div class="home-message">
        <h1>Nanami Komura's <br />Portfolio</h1>
        <p>
          welcome to my portfolio site. <br />
          This is my introduction and tech notes. <br />
          You can see tech records <br />
          in PLAYGROUND.
        </p>
        <Btn msg="go to PLAYGROUND" @click="clickHandler"></Btn>
      </div>
      <div id="topAnimation" ref="topAnimation" class="animation-top"></div>
    </div>

    <div class="skills-heading">skills</div>
    <div class="skills-container">
      <div class="skills">
        <div class="skills-box">
          <img alt="i1" src="../assets/svg/I1.svg" />
          <h2>Engineer</h2>
          <div>HTML5</div>
          <div>CSS3</div>
          <div>JavaScript</div>
          <div>Vue.js</div>
          <div>React</div>
        </div>
        <div class="skills-box">
          <img alt="i1" src="../assets/svg/I1.svg" />
          <h2>Design</h2>
          <div>AdobeXD</div>
          <div>Photoshop</div>
          <div>Illustrator</div>
        </div>
        <div class="skills-box">
          <img alt="i1" src="../assets/svg/I1.svg" />
          <h2>Architect</h2>
          <div>ArchiCAD</div>
          <div>Twinmotion</div>
          <div>Rhinoceros</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import lottie from "lottie-web";
import { useRouter } from "vue-router";
import Btn from "@/components/atoms/Btn.vue";
import A1 from "@/assets/Animation/F1/A1.json";
import A2 from "@/assets/Animation/F2/A2.json";

export default defineComponent({
  components: { Btn },
  name: "Home",
  mounted() {
    lottie.loadAnimation({
      container: this.$refs.lottie as Element,
      renderer: "svg",
      loop: true,
      autoplay: true,
      animationData: A1,
    });
    lottie.loadAnimation({
      container: this.$refs.topAnimation as Element,
      renderer: "svg",
      loop: true,
      autoplay: true,
      animationData: A2,
    });
  },
  setup() {
    const router = useRouter();

    const clickHandler = () => {
      console.log("clicked");
      router.push({ name: "Playground" });
    };
    return { clickHandler };
  },
});
</script>

<style lang="scss" scoped>
.shape {
  &-top {
    position: absolute;
    z-index: -1;
    top: -1150px;
    right: -2000px;
  }

  &-bottom {
    position: absolute;
    z-index: -1;
    top: 1400px;
    right: -200px;
    width: 2600px;
  }
}

.animation {
  &-top {
    position: absolute;
    right: 10vw;
    width: 600px;
    z-index: 5;
    top: 100px;
  }
}

.home {
  padding: 0 40px;

  &-message {
    padding: 170px 0;
    font-size: 20px;
  }
}

.skills {
  display: flex;
  justify-content: space-between;

  &-container {
    width: 850px;
    margin: 0 auto;
    margin-bottom: 100px;
  }

  &-heading {
    font-size: 30px;
    text-align: center;
    padding-bottom: 60px;
  }

  &-box {
    padding: 20px;
    box-shadow: 1px 1px 3px rgba(70, 62, 62, 0.15);
  }

  &-box img {
    width: 200px;
  }
}
</style>
