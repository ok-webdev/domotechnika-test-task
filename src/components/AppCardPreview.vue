<template>
  <router-link :to="{path: `details/${slug}`}" class="card">
    <img v-if="image === ''" src="../assets/img/logo.jpg" alt="No image" class="card__img">
    <img v-else :src="image" alt="Image" class="card__img">
    <div class="card__text">
      <p class="card__date">{{datePublish}}</p>
      <a class="card__title">
        <h2>{{title}}</h2>
      </a>
      <p class="card__tagline">
        {{shortText}}
      </p>
    </div>
  </router-link>
</template>

<script>
  export default {
    props: [
      'title',
      'datePublish',
      'shortText',
      'image',
      'slug'
    ]
  }
</script>

<style scoped>
  .card {
    max-height: 200px;
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    cursor: pointer;
    overflow-y: hidden;
    text-decoration: none;
  }
  .card__img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 10px;
  }
  .card__text {
    padding: 5px 16px;
    font-weight: 400;
  }
  .card__date {
    font-size: 13px;
    color: rgba(0, 0, 0, 0.5);
  }
  .card__title{
    font-size: 20px;
    letter-spacing: .15px;
    color: #1D5AB6;
    text-decoration: none;
    margin-top: 7px;
  }
  .card__tagline{
    font-size: 16px;
    color: rgba(0, 0, 0, 0.8);
    margin-top: 5px;
  }

  @media screen and (max-width: 1024px) {
    .card {
      width: 80%;
      max-height: 400px;
    }
  }
</style>