<template>
  <div class="card">
    <img :src="discsObject.poster" :alt="discsObject.title">
    <div class="card-text">
      <h2>{{ discsObject.title }}</h2>
      <h4>{{ discsObject.author }}</h4>
      <h5>{{ discsObject.year }}</h5>

    </div>
  </div>
</template>
  
  <script>

export default {
  name: 'MyCard',
  props: {
    discsObject: Object
  }
}
</script>
  
  <style lang="scss">
.card{
  background-color: #2E3A46;
  width: calc(100% / 5 - 40px);
  text-align: center;
  color: white;
  margin: 10px 20px;

  img{
    width: 80%;
    height: 170px;
    object-fit: contain;
  }

  .card-text{
    padding-bottom: 15px;
    h2{
      margin-bottom: 25px;
    }

    h4,h5{
      color: #808080;
    }
  }
}
</style>