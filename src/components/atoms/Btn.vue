<template>
  <div style="display: flex">
    <button
      class="btn"
      :style="{ 'background-color': backColor, color: textColor }"
      @click="showPwd = true"
    >
      {{ msg }}
    </button>
    <div v-if="hello" class="hello">
      <div v-if="showPwd">I'm clicked</div>
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
    return {
      ...toRefs(state),
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
}
</style>
