<template>
<div class="home">Home
  <p>My name is {{ name }} and my age is {{ age }}</p>
  <button @click="handleClick">click me</button>
</div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'HomeView',
  setup(){
    console.log('this')

    const p = ref()

    let name = 'felipe'
    let age = 37

    const handleClick= () => {
      console.log('you clicked me')
    }

    return {name, age, handleClick}
  }
  }
</script>
