<template>
  <div class="home">
   Home
   <p ref="p" class='test'>My name is {{name}} and my age is {{age}}</p>
   <button @click="handleclick">handle click</button>
     <button  @click="age++">Add age</button>
   <input v-model="name">
  </div>
</template>

<script>
// @ is an alias to /src
import {ref} from 'vue'

export default {
  name: 'Home',
 setup(){
const name=ref('mario')
const age =ref(30)
//ADDING NEW REF
const p=ref(null)
const handleclick=()=>{
//displaying ref value
  console.log(p,p.value)
  name.value="brian"
  age.value="27"
  // alert(p.value)

  //ADDING CLASS TO ABOVE REF
  p.value.classList.remove('test');
  p.value.textContent='Hello worias';

}


return {
  name,age,handleclick,p
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