<template>
  <div class="bg-black bg-black py-20">
    <div
      class="w-full max-w-sm mx-auto overflow-hidden bg-white rounded-lg shadow-md dark:bg-gray-800"
    >
      <div class="px-6 py-4">
        <h2
          class="text-3xl font-bold text-center text-gray-700 dark:text-white"
        >
          Brand
        </h2>

        <h3
          class="mt-1 text-xl font-medium text-center text-gray-600 dark:text-gray-200"
        >
          Welcome
        </h3>

        <p class="mt-1 text-center text-gray-500 dark:text-gray-400">
          Create Account
        </p>

        <form action="#" @submit.prevent="registration"   method="POST" >
          <!-- fname -->
          <div  class="w-full mt-4">
            <input id="fname"
            pattern="[a-zA-Z]{1,}"
              v-model="fname"
              class="block w-full px-4 py-2 mt-2 text-gray-700 placeholder-gray-500 bg-white border rounded-md dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 focus:border-blue-400 dark:focus:border-blue-300 focus:ring-opacity-40 focus:outline-none focus:ring focus:ring-blue-300"
              type="text"
              placeholder="First Name"
              aria-label="First Name"
              required  
            />
            <p id="demo" class="text"></p>
          </div>
          <!-- lname -->
          <div  class="w-full mt-4">
            <input
            id="lname"
              v-model="lname"
              class="block w-full px-4 py-2 mt-2 text-gray-700 placeholder-gray-500 bg-white border rounded-md dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 focus:border-blue-400 dark:focus:border-blue-300 focus:ring-opacity-40 focus:outline-none focus:ring focus:ring-blue-300"
              type="text"
              pattern="[a-zA-Z]{1,}"
              placeholder="Last Name"
              aria-label="Last Name"
            />
            
          </div>

          <!-- email -->
          <div class="w-full mt-4">
            <input id="email"
              v-model="email"
              class="block w-full px-4 py-2 mt-2 text-gray-700 placeholder-gray-500 bg-white border rounded-md dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 focus:border-blue-400 dark:focus:border-blue-300 focus:ring-opacity-40 focus:outline-none focus:ring focus:ring-blue-300"
              type="email"
              required
              placeholder="Email Address"
              aria-label="Email Address"
            />
          </div>
          <div class="w-full mt-4">
            <input
              v-model="password"
              class="block w-full px-4 py-2 mt-2 text-gray-700 placeholder-gray-500 bg-white border rounded-md dark:bg-gray-800 dark:border-gray-600 dark:placeholder-gray-400 focus:border-blue-400 dark:focus:border-blue-300 focus:ring-opacity-40 focus:outline-none focus:ring focus:ring-blue-300"
              type="password"
              placeholder="Password"
              aria-label="Password"
            />
          </div>

          <div class="flex items-center justify-between mt-4">
            <button 
              class="px-4 py-2 leading-5 text-white transition-colors duration-200 transform bg-gray-700 rounded hover:bg-gray-600 focus:outline-none"
              type="submit"
            >
              Register
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Swal from "sweetalert2";
export default {
  data(){
    return {
      // API_KEY:config.getApi.apiKey,
      getKey:process.env.Key,
       fname: "",
      lname: "",
      email: "",
      password: "",
      // checkForm: false,
      // FORM VARIABLE
       validEmail: '/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/g',
      redex:'[A-Za-z]'
    }

  },
   
    methods: {
    //   validateForm(){
    //   // console.log("working")
    // const fname = document.getElementById("fname");
    // const lname = document.getElementById("lname");
    // const email = document.getElementById("email");
    // // const email=document.getElementById("id2");
    
    // if(!fname.checkValidity()) {
    //     document.getElementById("demo").innerHTML = fname.validationMessage;
    //       //  document.getElementById("demo").innerHTML = lname.validationMessage;
    // }else if(!lname.checkValidity()){
    //    document.getElementById("demo2").innerHTML = lname.validationMessage;

    // }else if (!email.checkValidity()) {
    // //  document.getElementById("demo3").innerHTML = email.validationMessage;
    // } else{

    // };

     

    // },
    // FORM VALIDATION METHOD       
    registration() {
      console.log(this.getKey)
      // this. validateForm()

      var axios = require("axios");
      var data = JSON.stringify({
        email: this.email,
        firstName: this.fname,
        lastName: this.lname,
        password: this.password,
        
      });

      var config = {
        method: "post",
        url: "https://sugaryreading.backendless.app/api/data/Users",
        headers: {
          "Content-Type": "application/json",
          "x-api-key":this.getKey
        },
        data: data,
      };

      axios(config)
        .then(function (response) {
          // console.log(JSON.stringify(response.data));
          Swal.fire("Registration Sucessful");
          // window.location.href = "/login";
        })
        .catch(function (error) {
          console.log(error);
          Swal.fire("NOT Sucessful");
        });
    },
   
  },
  };

 

</script>

<style></style>
