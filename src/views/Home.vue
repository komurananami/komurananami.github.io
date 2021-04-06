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

.home {
  padding: 0 40px;

  &-message {
    padding: 170px 0;
    font-size: 20px;
  }
}
</style>
