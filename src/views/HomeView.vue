<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p >{{eiOne.name}} - {{eiOne.age}} - {{nameOne}}</p> 
    <!-- Name is change by input value .This is so cool (like DEMO)  -->
    <button @click="updateeiOne">Refs Btn</button>

    <h2>Reactive</h2>
    <p>{{eiTwo.name}} - {{eiTwo.age}} - {{nameTwo}}</p>
    <button @click="updateeiTwo">Reactive Btn</button>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import {ref,reactive} from 'vue'
export default {
  name: 'Home',
  setup(){
    
    // refs vs reactive (refs is can use One,refs is need value / reactive is can not use One,reactive no need value)
    const eiOne=ref({name:'Ei Phoo',age:20})
    const eiTwo=reactive({name:'Su Su',age:22})

    //ref can use one 
    const nameOne=ref('ei phoo')
    
    // this is not reactive value, this is just primitive value (So,reactive can not use One)
    const nameTwo=reactive('su su') 
    
    const updateeiOne = ()=>{
      eiOne.value.age=30
      nameOne.value="Ei" 
      // this can change as Ei
    }
    const updateeiTwo=()=>{
      eiTwo.age=40
      nameTwo=reactive("SU")
      // this can not change as SU
    }
    return{eiOne,updateeiOne,eiTwo,updateeiTwo,nameOne,nameTwo}
  }
 
  
}
</script>
