<template>
  
  <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
        <th scope="col">Name</th>
        <th scope="col">Age</th>
      
    </tr>
  </thead>
  <tbody>
    <tr v-for="(userData, index) in userData" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ userData.name }}</td>
          <td>{{ userData.age }}</td>
          <td>{{ userData.role }}</td>
        </tr>
  </tbody>
</table>


  
</template>

<script>
export default {
  name: 'ChildTwo',
  props: {
    userData: {
      type: Array,
      required: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
