<template>
  <div>
    <button
      class="btn"
      :style="{ 'background-color': backColor, color: textColor }"
    >
      {{ msg }}
    </button>
    <div v-if="hello">hello world</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

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
</style>
