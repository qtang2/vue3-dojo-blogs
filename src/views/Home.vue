<template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{ninjaOne.name}} - {{ninjaOne.age}}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <h2>Reactive</h2>
    <p>{{ninjaTwo.name}} - {{ninjaTwo.age}}</p>
    <button @click="updateNinjaTwo">Update ninja two</button>
    
    <!-- Home
    <p >My name is {{name}} and my age is {{age}}</p>
    <button @click="handleClick">Click Me</button>
    <button @click="age++">Add One To Age</button>
    <input type="text" v-model="name"> -->
  </div>
</template>

<script>
import { ref,reactive } from 'vue'

export default {
  name: 'Home',
  setup(){
    const ninjaOne = ref({name:'mario',age:30})
    const ninjaTwo = reactive({name:'luigi',age:35})
    const updateNinjaOne = ()=>{
      ninjaOne.value.age =40
    }
    const updateNinjaTwo = ()=>{
      ninjaTwo.age =45
    }

    return {ninjaOne,updateNinjaOne,updateNinjaTwo,ninjaTwo}
    // console.log('setup')
    //those two variables are not reactive 
    //which means when it updates, this wont reflect on page
    
    //use ref to surround a value makes the value reactive
    //which means it will updated in the dom when the reactive value get changed

    //const means the ref obj cannot change 
    //not mean , the value inside can change 
    // const name = ref('mario')
    // const age = ref(30)

    // const handleClick = () =>{
    //   name.value = 'luigi'
    //   // p.value.classList.add('test')
    //   // p.value.contentText = "Helllo"
    // }

    // return {name, age,handleClick}

  }
}
  
</script>
