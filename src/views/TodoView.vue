<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "TODOVIEW",
  setup() {
    const message = ref("");

    return {
      message,
    };
  },
});
</script>

<template>
  <div>
    <h2>할 일 목록</h2>

    <!-- 할 일 목록 폼 -->
    <input type="text" v-model="message" />
    <div>{{ message }}</div>

    <!-- 할 일 목록을 그린다. -->
  </div>
</template>
