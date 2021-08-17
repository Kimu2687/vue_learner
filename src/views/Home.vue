<template>
  <div class="home">
   Home
   <p ref="p" class='test'>My name is {{ninjaObject.name}} and my age is {{ninjaObject.age}}</p>
   <button @click="handleclick">handle click</button>
     <!-- <button  @click="ninjaObject.age++">Add age</button> -->
   <input v-model="ninjaObject.name">
  </div>
</template>

<script>
// @ is an alias to /src
import {ref} from 'vue'

export default {
  name: 'Home',
 setup(){

//USING OBJECTS
const ninjaObject=ref({ name:'mario', age :'30'})




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


return {
  handleclick,p,ninjaObject
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