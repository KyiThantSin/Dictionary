<template>
  <img src="../assets/rocket.gif" alt="rocket" id="rocket">
  <div class="home">
    <h1>Student's Helper</h1>
    <p>This website is built to help students find books, understand dictionary with example sentences.</p>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Home',
  components: {
    
    
  }
}
</script>

<style scoped>
  .home{
    margin-top: 10px;
  }
  p{
    font-size: 18px;
  }
  #rocket{
    width: 30%;
  }
</style>