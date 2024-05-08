<template> 
  <div class="container">
    <form>
  <div class="mb-3">
    <label for="exampleInputName" class="form-label">Name</label>
    <input type="text" class="form-control" id="exampleInputtext1" v-model="name">
  </div>
  <div class="mb-3">
    <label for="exampleInputAge" class="form-label">Age</label>
    <input type="number" class="form-control" id="exampleInputAge1" v-model="age">
  </div>
  <select class="form-select" aria-label="Default select example" v-model="role">
  <option value="admin">admin</option>
  <option value="user">user</option>
</select>
  <button @click="$emit('send',[name,age,role])" class="btn btn-primary mt-3 mb-5">Submit</button>
</form>
  </div>   
 

  </template>
  
  <script>
  export default {
    name: 'ChildOne',
    emits:['send'],
    data(){
      return{
        
      } 
    },
  }
  </script>
  
  <style scoped>
  
  </style>
  