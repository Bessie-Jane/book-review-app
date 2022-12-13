<template>
  <div class="picture-bg">
    <div class="bg-trans">
      <div class="home-body">

        <h6 class="home-body-header">Welcome to your one stop site for trusted reviews!</h6>
        <p class="body-text">Get amazing reveiws on books you love.</p>

        <router-link to="/get.review" tag="button">Get Reviews</router-link>

        <!-- <button @click="navigateToHome">Get Reviews</button> -->

      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  
  // methods: {
  //   navigateToHome() {
  //     this.$router.push('/homepage')
  //   }
  // }

}
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Sofia');
  @import url('https://fonts.googleapis.com/css?family=Asar');
  @import url('https://fonts.googleapis.com/css?family=Aclonica');


  .picture-bg {
    background: url('../assets/images/LibraryImg.jpg') no-repeat center center/cover;
    height: 100vh;
    width: 99vw;
  }

  .bg-trans {
    background-color: rgba(101, 42, 14, 0.3);
    /* background-color: rgba(74, 55, 40, 0.4); */
    height: 100vh;
  }

  .home-body {
    color: #fff;
    padding: 15% 0 0 50px;
  }

  .home-body-header{
    font-family: "Sofia", sans-serif;
    font-size: 50px;
    margin-bottom: 40px;
  }

  .body-text {
    font-family: "Asar", sans-serif;
    font-size: 30px;
    margin-bottom: 20px;
  }

  .home-body button{
    font-family: "Aclonica", sans-serif;
    text-transform: uppercase;
    background-color: #feb63e;
    padding: 6px 20px;
    border-radius: 3px;
  }

</style>
