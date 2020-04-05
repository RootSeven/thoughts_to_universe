<template>
<div class="the-universe">
  <h2>~ the Universe ~</h2>
  <br>
  <div class="the-universe-thoughts">
    <p v-on:click="handlePopThought" v-for="(thought, index) in thoughts" :key="index">{{ thought }}</p>
  </div>
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
  },

  methods: {
    handlePopThought (thought) {
      let thoughtText = (thought.target.textContent);
      this.thoughts.splice(this.thoughts.indexOf(thoughtText), 1)
    }
  }
}
</script>

<style scoped>
 .the-universe {
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

  .the-universe-thoughts > p  {
    font-style: italic;
    border: 3px solid white;
    margin-top: 10px;
    margin-bottom: 10px;
    padding: 10px;
    border-radius: 10px;
    width: 30%;
  }
</style>