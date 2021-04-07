<template>
  <p>Today's date : {{ today }}</p>
  <p>Current Time : {{ time }}</p>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import dayjs from "dayjs";
import localizedFormat from "dayjs/plugin/localizedFormat";

dayjs.extend(localizedFormat);

export default defineComponent({
  setup() {
    const now = dayjs();
    console.log("now", now.format("LL"));
    const today = now.format("LL");
    const time = now.format("LT");

    return { today, time };
  },
});
</script>
