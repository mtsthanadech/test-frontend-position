<template>
  <div class="row no-gutters profile">
    <div class="col-8">
      <div class="boxShowProfile">
        <img class="profileImage" :src="profileImage" alt="">
        <div class="profileName">{{name}}</div>
        <div class="profileSubtitle">{{job}}</div>
        <button type="button" class="btn btn-profile" role="button">
          Follow
        </button>
        <button type="button" class="btn btn-profile" role="button">
          Message
        </button>
      </div>
    </div>
    <div class="col-4">
      <div class="boxShowValue">
        <div class="profileValue">{{posts}}</div>
        <div class="profileSubvalue">Posts</div>
      </div>
      <div class="boxShowValue">
        <div class="profileValue">{{likes}}</div>
        <div class="profileSubvalue">Likes</div>
      </div>
      <div class="boxShowValue">
        <div class="profileValue">{{followers}}</div>
        <div class="profileSubvalue">Followers</div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "profile",
    props: ["name", "job", "profileImage", "posts", "likes", "followers"]
  }
</script>

<style scoped>
  .profile {
    height: 450px;
    border-radius: 20px;
    box-shadow: 0 15px 35px rgba(50,50,93,.1),0 5px 15px rgba(0,0,0,.07);
  }
  .btn-profile{
    color: #7A6455;
    border: 1px solid #7A6455;
    border-radius: 20px;
    padding-left: 20px;
    padding-right: 20px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  .btn-profile:hover{
    color: #FFFFFF;
    background: #7A6455;
    border: 1px solid #7A6455;
    border-radius: 20px;
    padding-left: 20px;
    padding-right: 20px;
    font-weight: bold;
  }
  .boxShowProfile {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    height: 100%;
  }
  .boxShowValue {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background: #F5E8DF;
    border: 1px solid #FFFFFF;
    height: 150px;
  }
  .boxShowValue:first-child {
    border-radius: 0 20px 0 0;
  }
  .boxShowValue:last-child {
    border-radius: 0 0 20px 0;
  }
  .profileImage {
    width: 100px;
    border: 3px solid #7A6455;
    border-radius: 50%;
    margin-bottom: 20px;
  }
  .profileName, .profileValue, .profileSubvalue, .profileSubtitle {
    color: #7A6455;
  }
  .profileName, .profileValue {
    font-size: 24px;
    font-weight: bolder;
  }
  .profileSubtitle {
    margin-bottom: 50px;
  }
</style>