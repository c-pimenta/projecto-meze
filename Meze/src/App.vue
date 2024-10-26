<script setup lang="ts">
import { ref } from 'vue';

const answer = ref("") //we are telling vue that every time that answer changes it needs to paint the template again
const onClick = () => {
  if (Math.random() >= 0.5) {
    answer.value = "Yes" // .value its the way to modify a ref
  } else {
    answer.value = "No"
  }

}

</script>

<template>
  <main>
    <button v-if="!answer" @click="onClick">Click me</button>
    <br>
    <h3 class="answer" v-text="answer" v-if="answer"></h3>
  </main>
</template>

<style scoped>
.answer {
  font-size: 2rem;
  font-family: Arial, Helvetica, sans-serif;
  color: crimson;
  border: solid 2px crimson;

  padding: 20px;
  border-radius: 30px;
}
</style>
