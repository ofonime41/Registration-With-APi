<template>
    <div>
      <h1>Welcome {{name}}</h1>
    </div>
  </template>
  
  <script>
  export default {
     
      data(){
          return{
            name:''
  
          }
          
      },
      mounted(){
         this.name=localStorage.getItem('FirstName');
         this.name=this.name.replace('"','');
         this.name=this.name.replace('"','');
         
      },
  
  }
  </script>
  
  <style>
  
  </style>