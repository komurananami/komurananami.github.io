<template>
  <div class="container">
    <Dayjs />
  </div>
  <div class="container">
    <Btn msg="I'm component" />
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
