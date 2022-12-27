<template>
  <div class="home">
    home
    <p >My name is {{name}} and my age is {{age}}</p> 
    <!-- Name is change by input value .This is so cool (like DEMO)  -->
    <button @click="handleClick">Clickme</button>
    <button @click="age++">Age+</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import {ref} from 'vue'
export default {
  name: 'Home',
  setup(){
    
    //this is reactive value
    const name=ref('Ei Phoo')
    const age =ref(22)

    const handleClick = ()=>{
      name.value="Shun"
      age.value=30
    }
    return{name, age, handleClick}
  },
  data(){
    return{
      score:30
    }
  }
 
  
}
</script>
