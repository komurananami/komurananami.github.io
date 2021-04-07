<template>
  <div style="display: flex">
    <button
      class="btn"
      :style="{ 'background-color': backColor, color: textColor }"
      @click="clickHandler"
    >
      {{ msg }}
    </button>

    <div v-if="hello" class="hello">
      <transition name="fade">
        <div v-if="showPwd">I'm clicked</div>
      </transition>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  components: {},
  name: "Btn",
  props: {
    msg: String,
    backColor: {
      type: String,
      default: "#fe697d",
    },
    textColor: {
      type: String,
      default: "#ffffff",
    },
    hello: Boolean,
  },
  setup() {
    console.log("hello");
    const state = reactive({
      showPwd: false,
    });

    const clickHandler = () => {
      state.showPwd = true;
      setTimeout(() => {
        state.showPwd = false;
      }, 2500);
    };
    return {
      ...toRefs(state),
      clickHandler,
    };
  },
});
</script>

<style lang="scss" scoped>
.btn {
  border-radius: 20px;
  font-weight: bold;
  font-size: 15px;
  cursor: pointer;
  border: none;
  padding: 10px 15px;
  box-shadow: 0 0.2em 0.5em rgba(0, 0, 0, 0.2);
}

.hello {
  padding-left: 40px;
  padding-top: 10px;
  font-weight: bold;
}

.fade-enter-active {
  transition: all 0.3s ease-out;
}

.fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.fade-enter-from,
.fade-leave-to {
  transform: translateX(-20px);
  opacity: 0;
}
</style>
