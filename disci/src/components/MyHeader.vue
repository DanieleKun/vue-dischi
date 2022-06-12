<template>
  <header>
    <img src="../assets/logo-spotify.png" alt="">
  </header>
</template>

<script>

  export default {
    name: 'MyHeader',
  }
</script>

<style lang="scss">

  header {
    height: 80px;
    background-color: #2E3A46;
    display: flex;
    align-items: center;

    img{
      width: 50px;
      margin-left: 20px;
    }
  }

</style>