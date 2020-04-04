<template>
  <div>
    <h2>~ think ~</h2>
    <br>
    <p>send a thought out to the Universe</p>
    <br>
    <form v-on:submit.prevent>
      <input v-model="thought" placeholder="Penny for your thoughts..." type="text">
      <br>
      <button v-on:click="handleSubmitThought">transmit energy</button>
    </form>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  methods: {
    handleSubmitThought: function() {
      eventBus.$emit('send-thought-to-universe', this.thought);
      this.thought = "";
    }
  },
  data() {
    return {
      thought: ""
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
    border: 6px blue double;
    border-radius: 50px;

    background: rgb(21,21,219);
    background: linear-gradient(180deg, rgba(21,21,219,1) 0%, rgba(15,15,73,1) 28%);
  }

  input {
    width: 30%;
    border-radius: 50px;

  }

  p {
    font-style: italic;
  }

  button {
    width: 100px;
    color: white;
    background-color: rgb(15, 15, 73);
    border: 1px solid white;
  }
</style>