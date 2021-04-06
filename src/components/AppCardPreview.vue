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
    display: flex;
    align-items: flex-start;
    justify-content: flex-start;
    cursor: pointer;
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
    text-decoration: none;
  }
  .card__title h2 {
    font-size: 20px;
    letter-spacing: .15px;
    color: #1D5AB6;
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
    }
  }
  @media screen and (max-width: 768px) {
    .card {
      width: 80%;
      flex-direction: column;
    }
    .card__img {
      max-width: 150px;
      max-height: 150px;
      aspect-ratio: (1, 1);
    }
    .card__text {
      padding: 0;
      margin-top: 15px;
    }
  }
</style>