<script lang="ts">
import { useCounterStore } from "@/stores/counter";
import { storeToRefs } from "pinia";
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "HomeView",
  setup() {
    const count = ref(0);

    const counterStore = useCounterStore();
    const { count: pCount, increment } = storeToRefs(counterStore);

    const handleAdd = () => {
      console.log("dfsfsd");
      count.value++;
    };

    const handleMinus = () => {
      console.log("minus");
      count.value--;
    };

    const handleReset = () => {
      counterStore.$patch({ count: 0 });
    };

    return {
      count,
      pCount,
      increment,
      handleAdd,
      handleMinus,
      handleReset,
    };
  },
});
</script>

<template>
  <main>
    <span>{{ count }}</span>

    <div>
      <button @click="handleAdd">+</button>
      <button @click="handleMinus">-</button>
    </div>

    <h2>Pinia Counter</h2>
    <span>{{ pCount }}</span>
    <button @click="increment">+</button>
    <button @click="handleReset">reset</button>

    <router-link to="/todo"> 할일 목록으로 이동 </router-link>
  </main>
</template>
