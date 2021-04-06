<template>
  <div class="item">
    <h2>{{title}}</h2>
    <div class="item__content">
      <img v-if="image === ''" src="../assets/img/logo.jpg" alt="No image" class="item__img">
      <img v-else :src="image" alt="Image" class="item__img">
      <p class="item__text" v-html="text"></p>
    </div>
  </div>
</template>

<script>
  export default {
    props: [
      'title',
      'datePublish',
      'text',
      'image',
      'slug'
    ]
  }
</script>

<style scoped>
  h2{
    font-size: 28px;
    color: rgba(0, 0, 0, 0.8);
    text-align: left;
  }
  .item__content{
    width: 70%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    margin-top: 10px;
  }
  .item__img{
    width: 284px;
    height: 284px;
    object-fit: cover;
    border-radius: 10px;
  }
  .item__text{
    font-size: 16px;
    line-height: 140%;
    color: rgba(0, 0, 0, 0.8);
    margin-left: 15px;
  }

  @media screen and (max-width: 768px) {
    .item__content {
      width: 95%;
      flex-direction: column;
    }
    .item__text{
      width: 100%;
      margin: 20px;
    }
  }
</style>