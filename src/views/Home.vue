<template>
  <div class="container">
    <img alt="shape-green" src="../assets/blob.svg" class="shape-bottom" />
    <img alt="shape-top" src="../assets/blob.svg" class="shape-top" />

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

    <div class="skills-container">
      <div class="skills-heading">skills</div>
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

    <div class="works-container">
      <div class="works-heading">works</div>
      <div class="works-section">
        <div class="works-img" id="lottie" ref="lottie"></div>
        <div class="works">
          <div>coming soon...</div>
          <div>coming soon...</div>
          <div>coming soon...</div>
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
    top: -950px;
    right: -1800px;
    width: 3000px;
    @media screen and (max-width: 1200px) {
      right: -2100px;
    }
    @media screen and (max-width: 768px) {
      top: -650px;
      right: -1500;
    }
  }

  &-bottom {
    position: absolute;
    z-index: -1;
    top: 1400px;
    right: -200px;
    width: 2600px;
    @media screen and (max-width: 768px) {
      top: 2600px;
      right: -600px;
    }
  }
}

.animation {
  &-top {
    width: 700px;
    z-index: 5;
    @media screen and (max-width: 1200px) {
      width: 500px;
    }
    @media screen and (max-width: 768px) {
      width: 300px;
      margin: 0 auto;
      padding-left: 160px;
    }
  }
}

.home {
  display: flex;
  justify-content: center;

  @media screen and (max-width: 768px) {
    flex-direction: column;
  }

  &-message {
    padding: 170px 0px 170px 100px;
    font-size: 20px;

    @media screen and (max-width: 1200px) {
      padding: 170px 30px 170px 50px;
      margin: 0 auto;
    }
    @media screen and (max-width: 768px) {
      margin: 0 auto;
      padding: 170px 50px 0 50px;
    }
  }
}

.skills {
  display: flex;
  justify-content: center;
  @media screen and (max-width: 768px) {
    flex-direction: column;
  }

  &-container {
    margin-bottom: 100px;
    @media screen and (max-width: 1200px) {
      width: 100%;
    }
    @media screen and (max-width: 768px) {
      width: 100%;
    }
  }

  &-heading {
    font-size: 30px;
    text-align: center;
    padding: 60px 0;
  }

  &-box {
    padding: 30px;
    margin: 30px;
    box-shadow: 1px 1px 3px rgba(70, 62, 62, 0.15);
    @media screen and (max-width: 1200px) {
      padding: 20px;
      margin: 20px;
    }
    @media screen and (max-width: 768px) {
      padding: 60px;
      margin: 20px auto;
    }
  }

  &-box img {
    width: 200px;
    @media screen and (max-width: 1200px) {
      width: 20vw;
    }
    @media screen and (max-width: 768px) {
      width: 200px;
    }
  }
}

.works {
  display: flex;
  margin: 0 auto;
  @media screen and (max-width: 1200px) {
    margin: 0;
    justify-content: center;
  }
  @media screen and (max-width: 768px) {
    width: 450px;
    margin: 0 auto;
    flex-wrap: wrap;
    justify-content: start;
  }

  div {
    background: #fe697d;
    height: 150px;
    width: 160px;
    margin: 30px;
    color: white;
    text-align: center;
    line-height: 150px;
    box-shadow: 3px 5px 5px rgba(70, 62, 62, 0.15);
    @media screen and (max-width: 1200px) {
      margin: 20px;
    }
    @media screen and (max-width: 768px) {
      margin: 10px;
      height: 200px;
      width: 200px;
    }
  }

  &-container {
    margin: 0 auto;
    width: 1170px;
    @media screen and (max-width: 1200px) {
      width: 100%;
    }
    @media screen and (max-width: 768px) {
      width: 100%;
    }
  }

  &-heading {
    font-size: 30px;
    text-align: center;
    padding-bottom: 60px;
  }

  &-section {
    display: flex;
    justify-content: center;
    margin: 0 auto;
    @media screen and (max-width: 1200px) {
      width: 100%;
      flex-direction: column-reverse;
    }
  }

  &-img {
    width: 400px;
    @media screen and (max-width: 1200px) {
      width: 400px;
      margin-left: 80px;
    }
    @media screen and (max-width: 768px) {
    }
  }
}
</style>
