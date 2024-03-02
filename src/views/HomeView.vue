<script setup lang="ts">
import { ref } from "vue";

const count = ref(0);

const handleAdd = () => {
  console.log("dfsfsd");
  count.value++;
};

const handleMinus = () => {
  console.log("minus");
  count.value--;
};
</script>

<template>
  <main>
    <span>{{ count }}</span>

    <div>
      <button @click="handleAdd">+</button>
      <button @click="handleMinus">-</button>
    </div>
  </main>
</template>
