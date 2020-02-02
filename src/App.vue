<template>
  <div id="app">
<!--    <img alt="Vue logo" src="./assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <question1/>

    <br><br>

    <question2/>

    <br><br>

    <question3/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import question1 from "./views/question1";
import question2 from "./views/question2";
import question3 from "./views/question3";

export default {
  name: 'app',
  components: {
    // HelloWorld,
    question1,
    question2,
    question3
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
