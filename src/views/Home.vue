<template>
  <div class="home">
   Home
   <p ref="p" class='test'>My name is {{name}} and my age is {{age}}</p>
   <button @click="handleclick">handle click</button>
  </div>
</template>

<script>
// @ is an alias to /src
import {ref} from 'vue'

export default {
  name: 'Home',
 setup(){
let name='mario'
let age =30
//ADDING NEW REF
const p=ref(null)
const handleclick=()=>{
//displaying ref value
  console.log(p,p.value)
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