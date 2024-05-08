<template>
    <NavBar/>
    <ChildOne @send="HandleSend"/>
    <button @click="falg=='admin'">Admin</button>
    <button @click="falg=='user'">User</button>
    <ChildTwo :userData="flag == 'admin' ? admin : user" />

  </template>
  
  <script>
  import ChildOne from './ChildOne.vue'
  import ChildTwo from './ChildTwo.vue'
  import NavBar from './NavBar.vue'
  export default {
    name: 'HomePage',
    components:{
      ChildOne,
      ChildTwo,
      NavBar
    },
    data(){
      return{
    user: JSON.parse(localStorage.getItem('user')) || [],
    admin: JSON.parse(localStorage.getItem('admin')) || [],
    flag: 'admin'
      } 
    },
    methods: {
    HandleSend(data) {
      const [name, age, role] = data;

      if (role === "admin") {
        this.admin.push({ name, age, role });
        localStorage.setItem('admin', JSON.stringify(this.admin)); 
      } else if (role === "user") {
        this.user.push({ name, age, role });
        localStorage.setItem('user', JSON.stringify(this.user));
      }
      console.log(this.user);
      console.log(this.admin);
    }
  }
}
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  
  </style>