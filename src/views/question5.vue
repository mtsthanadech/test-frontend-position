<template>
  <label class="d-flex flex-column">
    <div class="changeKeyword">
      <!-- Change text to convert to camelcase -->
      <button type="button" class="btn btn-primary" role="button" @click="text = 'hello case'">hello case</button>
      <button type="button" class="btn btn-primary" role="button" @click="text = 'camel case word'">camel case word</button>
    </div>
    <!-- Input text to convert to camelcase -->
    <input class="form-control" type="text" placeholder="Enter what you want to convert to camelCase" v-model="text">
    <!-- Show result -->
    <div>{{camelCase(text)}}</div>
  </label>
</template>

<script>
  export default {
    name: "question5",
    data() {
      return {
        text: "Hello world"
      }
    },
    methods: {
      camelCase(value) {
        return value
          .replace(/\s(.)/g, (char) => {
            // Replace character after space with uppercase
            return char.toUpperCase();
          })
          // Replace all space with no space
          .replace(/\s/g, '')
          .replace(/^(.)/, (char) => {
            // Replace first character to lowercase
            return char.toLowerCase();
          });
      }
    }
  }
</script>

<style scoped>
  .changeKeyword {

  }
</style>