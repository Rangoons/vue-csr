<template>
  <ul>
    <li v-for="user in users" :key="user.id">
      <router-link :to="'/users/' + user.id">{{user.name}}</router-link>
    </li>
  </ul>
</template>

<script>
import axios from "axios";
export default {
  name: "Users",
  data() {
    return {
      users: []
    };
  },
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(res => {
        this.users = res.data;
      })
      .catch(err => console.log(err));
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
