<template>
  <profile
    :name="user.name"
    :job="user.job"
    :profileImage="user.profileImage"
    :posts="user.posts"
    :likes="user.likes"
    :followers="user.followers"/>
  <!-- Send property from parent component(question4_1) to child component(profile) -->
</template>

<script>
  import profile from "../components/profile";
  import profileImage from "../assets/Octocat.jpg"
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
          profileImage: profileImage,
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