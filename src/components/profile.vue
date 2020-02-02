<template>
  <div class="row">
    <div class="col-8">
      {{name}}
      {{job}}
    </div>
    <div class="col-4">
      <div class="boxShowValue">
        <div>{{posts}}</div>
        <div>Posts</div>
      </div>
      <div class="boxShowValue">
        <div>{{likes}}</div>
        <div>Likes</div>
      </div>
      <div class="boxShowValue">
        <div>{{followers}}</div>
        <div>Followers</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "profile",
    props: ["name", "job", "posts", "likes", "followers"]
  }
</script>

<style scoped>
  .boxShowValue {
    height: 150px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background: #F5E8DF;
    border: 1px solid #FFFFFF;
  }
</style>