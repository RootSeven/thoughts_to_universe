<template>
  <div>
    <ThinkForm></ThinkForm>
    <TheUniverse></TheUniverse>
  </div>
</template>

<script>
import ThinkForm from './components/ThinkForm';
import TheUniverse from './components/TheUniverse';

export default {
  components: {
    ThinkForm,
    TheUniverse
  }

}
</script>

<style>
  * {
    margin: 0 auto;
    padding: 0px;
    text-align: center;
  }

  body {
    background-color: rgb(15, 15, 73);
    color: white;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  }

  button {
    border: none;
    padding: 3px;
    margin: 10px;
    border-radius: 10px;
  }
  
  h1 {
    margin: 10px;
  }
</style>