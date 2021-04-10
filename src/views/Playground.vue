<template>
  <div class="con">
    <Dayjs />
    <div class="btn">
      <Btn msg="click me" hello />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Dayjs from "../components/atoms/Dayjs.vue";
import Btn from "../components/atoms/Btn.vue";

export default defineComponent({
  components: { Dayjs, Btn },
});
</script>

<style lang="scss" scoped>
.con {
  text-align: center;
  width: 1000px;
  margin: 80px auto;
  @media screen and (max-width: 1200px) {
    width: 700px;
  }
  @media screen and (max-width: 768px) {
    width: 500px;
  }
}

.btn {
  width: 240px;
  margin: 0 auto;
}
</style>
