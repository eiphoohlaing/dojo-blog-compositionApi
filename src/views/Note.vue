<template>
  <div class="home">
    home
    <p ref="p">My name is {{name}} and my age is {{age}}</p>
    <button @click="handleClick">Clickme</button>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import {ref} from 'vue'
export default {
  name: 'Home',
  setup(){
    console.log('setup')
    console.log(this)
    const p = ref(null)
    let name='Ei Phoo'
    let age ="22"

    const handleClick = ()=>{
      console.log(p,p.value)
      p.value.classList.add('test')
      p.value.textContent="Hello , Ei Phoo"
    }
    return{name, age, handleClick, p}
  },
  // data(){
  //   return{
  //     age:"30"
  //   }
  // }
  

//this is(Composition API) HomeView example
}
</script>
