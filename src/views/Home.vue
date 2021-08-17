<template>
  <div class="home">
   Home
   <p ref="p" class='test'>My name is {{ninjaObject.name}} and my age is {{ninjaObject.age}}</p>
   <button @click="handleclick">handle click</button>
     <!-- <button  @click="ninjaObject.age++">Add age</button> -->
   <input v-model="ninjaObject.name">

   <p>Reactive</p>
    <button @click="handleclick2">handle click</button>
   <p ref="p" class='test'>My name is {{ninjaObject2.name}} and my age is {{ninjaObject2.age}}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import {reactive, ref} from 'vue'

export default {
  name: 'Home',
 setup(){

//USING OBJECTS
const ninjaObject=ref({ name:'mario', age :'30'})
//REACTIVE OBJECTS
const ninjaObject2=reactive({ name:'mario', age :'30'})




//ADDING NEW REF
const p=ref(null)
const handleclick=()=>{
//displaying ref value
  console.log(p,p.value)
  ninjaObject.value.name="brian"
  ninjaObject.value.age="27"
  // alert(p.value)

  //ADDING CLASS TO ABOVE REF
  p.value.classList.remove('test');
  p.value.textContent='Hello worias';

}
const handleclick2=()=>{
//displaying ref value
  
  ninjaObject2.name="brian"
  ninjaObject2.age="27"
  // alert(p.value)

  //ADDING CLASS TO ABOVE REF
  // p.value.classList.remove('test');
  // p.value.textContent='Hello worias';

}


return {
  handleclick,p,ninjaObject,ninjaObject2,handleclick2
}
 }
}
</script> 
<style >
.test{
  background :green;
  color: white;
}

</style>