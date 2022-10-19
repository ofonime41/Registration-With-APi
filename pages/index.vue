<template>
  <Registration/>
  <!-- <div class="bg-blue-700 p-10">
    Enter a valid value
    <input id="id1" type="number" min="100" max="300" required>
  <p class="text-white-600" id="demo"></p>
  <br><br>
  <input id="id2" type="email" required>
  <p class="text-white-600" id="demo1"></p>
  <button class="bg-green-500 p-5 " @click="myFunction">submit</button>
  </div> -->


</template>

<script>
// import { onMounted } from 'vue';
import Registration from '../components/Registration.vue';
// import ValidateForm from '../components/validateForm.vue';
onMounted:{
  
}
export default {
    name: "IndexPage",
    components: { Registration },

    methods:{
  //     myFunction() {
  //     console.log("working")
  //   const inpObj = document.getElementById("id1");
  //   const email=document.getElementById("id2");
  //   if (!inpObj.checkValidity()) {
  //     document.getElementById("demo").innerHTML = inpObj.validationMessage;
  //   };
  //   if (!email.checkValidity()) {
  //     document.getElementById("demo1").innerHTML = email.validationMessage;
  //   }
  // }

    }

}
</script>
