<template>
  <div id="app">
    <div class="container">
      <div>

        <div class="questionBox">
          <!-- Title of the app -->
          <h4>Frontend Developer Questions - Junior & Mid Level</h4>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 1 (Show JSON array) -->
          <h5>Question 1</h5>
          <question1/>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 2 (To do lists) -->
          <h5>Question 2</h5>
          <question2/>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 3 (Find Unique) -->
          <h5>Question 3</h5>
          <question3/>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 4 (Profile) -->
          <h5>Question 4-1</h5>
          <question4_1/>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 4 (Button) -->
          <h5>Question 4-2</h5>
          <question4_2/>
        </div>
        <div class="questionBox">
          <!-- Answer of the question 5 (camelCase) -->
          <h5>Question 5</h5>
          <question5/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import question1 from "./views/question1";
import question2 from "./views/question2";
import question3 from "./views/question3";
import question4_1 from "./views/question4_1";
import question4_2 from "./views/question4_2";
import question5 from "./views/question5";

export default {
  name: 'app',
  components: {
    question1,
    question2,
    question3,
    question4_1,
    question4_2,
    question5
  }
}
</script>

<style scoped>
  .questionBox {
    width: 600px;
    margin-bottom: 50px;
  }
</style>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
