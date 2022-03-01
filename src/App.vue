<script setup lang="ts">
import { ref, watch } from "vue";

let getTaco = ref(true);
const question = ref("");

function getTacoClick() {
  console.log("clicked");
  getTaco.value = !getTaco.value;
}

// watch works directly on a ref
watch(getTaco, async (newQuestion, oldQuestion) => {
  console.log(oldQuestion);
  console.log("getTaco watcher");
  console.log(newQuestion);
});

// watch works directly on a ref
watch(question, async (newQuestion, oldQuestion) => {
  console.log(oldQuestion);
  console.log("question watcher");
  console.log(newQuestion);
});
</script>

<template>
  <div>
    <button @click="getTacoClick">Click me to order a taco</button>
    <h2>Where is my taco...</h2>
  </div>

  <input v-model="question" />
</template>
