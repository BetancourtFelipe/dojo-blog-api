<template>
<div class="home">
  <h1>Home</h1>
  <div v-if="error">{{ error }}</div>
  <div v-if="posts.length">
    <PostList :posts='posts' />
  </div>
  <div v-else>Loading....</div>


  <!-- Button to toggle the visibility of posts -->
  <!-- <button @click="showPosts = !showPosts">toggle posts</button> -->

  <!-- Button to delete the last post -->
  <!-- <button @click="posts.pop()">delete a post</button> -->



  <!-- <input type="text" v-model="search">
  <p>search term - {{ search }}</p>
  <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  <button @click="handleClick">stop watching</button> -->

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
import PostList from '../components/PostList.vue';
import getPosts from '../composables/getPosts';

export default {
  name: 'HomeView',
  components: {PostList},
  setup(){
    const { posts, error, load } = getPosts()

    load()







    // const showPosts = ref(true)

    // // Creating a ref named 'search' with an initial value of an empty string
    // const search = ref('')

    // // Creating a ref named 'names' with an initial array of names
    // const names = ref(['ivo', 'lukas', 'jalal', 'felipe', 'mandla', 'fabio', 'hoshi'])

    // // Using the watch function to observe changes in 'search'
    // // and executing a callback when it changes
    // const stopWatch = watch(search, () => {
    //   console.log('watch function')
    // })


    // // Using the watchEffect function to reactively execute a callback
    // // whenever the dependencies (in this case, 'search.value') change
    // const stopEffect= watchEffect(() => {
    //   console.log('watchEffect function', search.value)
    // })

    // // Using the computed function to create a computed property 'matchingNames'
    // // that filters 'names' based on whether each name includes the current 'search.value'
    // const matchingNames = computed(() =>{
    //   return names.value.filter((name) => name.includes(search.value))
    // })

    // const handleClick = () => {
    //    // Stopping the watch and watchEffect functions
    //   stopWatch()
    //   stopEffect()
    // }



    return{ posts, error }

     // Define reactive and ref properties
    // const ninjaOne = ref({ name: 'felipe', age: 29 })
    // const ninjaTwo = reactive({ name: 'lukas', age: 19})

       // Function to update ninjaOne's age using refs
    // const updateNinjaOne = () => {
    //   ninjaOne.value.age = 40
    // }

    // const updateNinjaTwo = () => {
    //   ninjaTwo.age = 55
    // }


    // Creating a ref named 'p' with an initial value of 'hello'
    // const p = ref('hello')

    // Logging the ref object 'p' and its current value to the console
    // console.log(p, p.value)

    // Creating refs for 'name' and 'age' with initial values
    // const name = ref('felipe')
    // const age = ref(37)

    // Defining a function named 'handleClick'
    // const handleClick = () => {
      // Logging the ref object 'p' and its current value to the console
      // console.log(p, p.value)

     // Adding a CSS class 'test' to the DOM element referred to by 'p'
      // p.value.classList.add('test')
     // Changing the text content of the DOM element referred to by 'p'
      // p.value.textContent= 'hello, ninjas'

    //    Changing the values of 'name' and 'age' refs

      // name.value = 'lukas'
      // age.value = 36

    }

    // The code above demonstrates the use of Vue's ref function to create reactive values.
// It initializes refs for strings ('p' and 'name') and a ref for a number ('age').
// The handleClick function showcases how to interact with the values referred to by refs.
// It logs values to the console, modifies the DOM element class and text content, and updates 'name' and 'age'.
}

</script>
