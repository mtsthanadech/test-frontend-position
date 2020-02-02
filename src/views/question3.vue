<template>
  <div>
    findUniq({{set0}}) return {{findUniq(set0)}}
    <br>
    findUniq({{set1}}) return {{findUniq(set1)}}
  </div>
</template>

<script>
  export default {
    name: "question3",
    data() {
      return {
        set0: [1, 1, 1, 2, 1, 1],
        set1: [0, 0, 0.55, 0, 0]
      }
    },
    methods: {
      findUniq(values) {
        let arr = [];
        let dup = [];

        for (let i = 0; i < values.length; i++) {
          if (!arr.includes(values[i])) {
            // Add values are unique to arr
            arr.push(values[i]);
          } else {
            // Add values are duplicate to dup
            dup.push(values[i]);
          }
        }

        for (let i = 0; i < arr.length; i++) {
          if (dup.includes(arr[i])) {
            // Remove duplicate value in arr by compare with dup
            arr.splice(i,1);
          }
        }

        // Return the first value of the arr
        return arr[0]
      }
    },
  }
</script>

<style scoped>

</style>