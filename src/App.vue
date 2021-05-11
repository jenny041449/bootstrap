<template>
<div>


  <div id="app">
 
    <!-- <pageIn01 v-if="open" /> -->
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
     </div>    v-if="!open" -->
    <router-view />
  </div></div>
</template>
 
<script>
// import pageIn01 from "@/components/pageIn01.vue";

export default {
  data() {
    return {
      open: true,
    };
  },
  methods: {},
  components: {
    // pageIn01,
  },
  mounted() {
    window.setInterval(() => {
      this.open = false;
      console.log(this.open)
    }, 8000);
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
