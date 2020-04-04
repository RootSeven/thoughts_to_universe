<template>
<div>
  <h2>~ the Universe ~</h2>
  <br>
  <p v-for="(thought, index) in thoughts" :key="index">{{ thought }}</p>
</div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  mounted() {
    eventBus.$on('send-thought-to-universe', (thought) => {
      this.thoughts.push(thought);
    })
  },

  data() {
    return {
      thoughts: []
    }
  }
}
</script>

<style scoped>
 div {
    padding: 20px;
    width: 50%;
    margin-top: 10px;
    margin-bottom: 10px;
    border: 6px double magenta;
    border-radius: 50px;

    background: rgb(21,21,219);
    background: linear-gradient(180deg, rgba(21,21,219,1) 0%, rgba(15,15,73,1) 28%);
  }

  input {
    width: 30%;
  }

  p {
    font-style: italic;
  }
</style>