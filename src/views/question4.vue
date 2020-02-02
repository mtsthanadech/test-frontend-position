<template>
  <profile
    :name="user.name"
    :job="user.job"
    :posts="user.posts"
    :likes="user.likes"
    :followers="user.followers"/>
</template>

<script>
  import profile from "../components/profile";
  export default {
    name: "question4",
    components: {
      profile
    },
    data() {
      return {
        user: {
          name: "Jessica Potter",
          job: "Visual Artist",
          posts: 523,
          likes: 1387,
          followers: 146
        }
      }
    }
  }
</script>

<style scoped>

</style>