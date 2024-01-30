<template>
<div class="home">Home
  <h1>Home</h1>
     <!-- Display info for ninjaOne using refs -->
  <!-- <h2>Refs</h2>
  <p>{{ ninjaOne.name }} - {{ ninjaOne.age }}</p>
  <button @click="updateNinjaOne">Update ninja one</button> -->

  <!-- <h2>Reactive</h2> -->
    <!-- Display info for ninjaTwo using reactivity -->
  <!-- <p>{{ ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
  <button @click="updateNinjaTwo">Update ninja one</button> -->


  <!-- <p>My name is {{ name }} and my age is {{ age }}</p>
  <button @click="handleClick">click me</button>
  <button @click="age++">add 1 to age</button>
  <input type="text" v-model="name"> -->

</div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
  name: 'HomeView',
  setup(){
     // Define reactive and ref properties
    const ninjaOne = ref({ name: 'felipe', age: 29 })
    const ninjaTwo = reactive({ name: 'lukas', age: 19})

       // Function to update ninjaOne's age using refs
    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }

    const updateNinjaTwo = () => {
      ninjaTwo.age = 55
    }


    // Creating a ref named 'p' with an initial value of 'hello'
    const p = ref('hello')

    // Logging the ref object 'p' and its current value to the console
    console.log(p, p.value)

    // Creating refs for 'name' and 'age' with initial values
    const name = ref('felipe')
    const age = ref(37)

    // Defining a function named 'handleClick'
    const handleClick = () => {
      // Logging the ref object 'p' and its current value to the console
      console.log(p, p.value)

     // Adding a CSS class 'test' to the DOM element referred to by 'p'
      p.value.classList.add('test')
     // Changing the text content of the DOM element referred to by 'p'
      p.value.textContent= 'hello, ninjas'

    //    Changing the values of 'name' and 'age' refs

      name.value = 'lukas'
      age.value = 36

    }

    // The code above demonstrates the use of Vue's ref function to create reactive values.
// It initializes refs for strings ('p' and 'name') and a ref for a number ('age').
// The handleClick function showcases how to interact with the values referred to by refs.
// It logs values to the console, modifies the DOM element class and text content, and updates 'name' and 'age'.


    return { ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo}
  }
}
</script>
