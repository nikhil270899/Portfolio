<template>
  <div class="hello">
    <General />

    <p class="create-class text-muted">
      created by
      <b-link href="/" class="link">nikhil</b-link> - devChallenges.io
    </p>
  </div>
</template>

<script>
import General from "./General.vue";
export default {
  name: "Portfolio",
  props: {
    msg: String,
  },
  components: {
    General,
  },
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
.create-class {
  text-align: center;
  margin-top: 50px;
}
.link {
  color: darkgrey;
}
</style>
