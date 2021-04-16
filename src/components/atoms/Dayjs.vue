<template>
  <p>Today's date : {{ state.today }}</p>
  <p>Current Time : {{ state.time }}</p>
</template>

<script lang="ts">
import { defineComponent, onUnmounted, reactive } from "vue";
import dayjs from "dayjs";
import localizedFormat from "dayjs/plugin/localizedFormat";

dayjs.extend(localizedFormat);

export default defineComponent({
  setup() {
    const now = dayjs();
    const state = reactive({
      today: now.format("LL"),
      time: now.format("LTS"),
    });

    const interval = setInterval(() => {
      const now = dayjs();
      const today = now.format("LL");
      const time = now.format("LTS");

      state.today = today;
      state.time = time;
      console.log(now);
    }, 1000);

    onUnmounted(() => {
      clearInterval(interval);
    });

    return { state, interval };
  },
});
</script>
