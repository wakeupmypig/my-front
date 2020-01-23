<template>
  <div id="app">
    <li v-for="(user) in users" :key="user.id">{{user.name}}</li>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'app',
  data(){
    return {
      users:[]
    }
  },
  async mounted(){
    let r = await axios.get('http://localhost:3000/api/user');
    this.users = r.data;
  }
}
</script>

<style>

</style>
