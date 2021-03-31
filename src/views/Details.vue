<template>
  <main class="main">
    <app-card-view 
        v-for="(element, key) in details" 
        :key="key"
        :image="element.image"
        :title="element.title"
        :text="element.text"
    />
  </main>
</template>

<script>
  import AppCardView from '../components/AppCardView'
  export default {
      data () {
      return {
        details: [],
        }
      },
      mounted() {
      fetch(`https://domotekhnika.ru/api/v1/news/${this.$route.params.slug}`).
        then(response => response.json()).
        then(data => {
          this.details = [data.data.news]
        })
    },
    components: {
      AppCardView
    }
  }
</script>

<style>
  
</style>