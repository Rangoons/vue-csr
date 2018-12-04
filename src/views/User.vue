<template>
  <div class="hello">
    <pre>{{user}}</pre>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "User",
  props: {
    id: Number
  },
  data() {
    return {
      user: {}
    };
  },
  mounted() {
    axios
      .get(`https://jsonplaceholder.typicode.com/users/${this.id}`)
      .then(res => {
        this.user = res.data;
      })
      .catch(err => console.log(err));
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
