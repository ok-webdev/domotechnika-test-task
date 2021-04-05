<template>
  <main class="main">
    <h1>{{title}}</h1>
    <div class="cards-wrapper">
      <app-card-preview 
        v-for="(element, key) in news" 
        :key="key"
        :image="element.image"
        :datePublish ="formatDate(element.datePublish)"
        :title="element.title"
        :shortText="element.shortText"
        :slug="element.slug"/>
    </div>
    <button @click="loadMore()" class="btn">Показать ещё</button>
  </main>
</template>

<script>
  import CardPreview from '@/components/AppCardPreview'

  export default {
    mounted () {
        fetch(`https://domotekhnika.ru/api/v1/news?page=1`).
        then(response => response.json()).
        then(data => {
          this.news = [...data.data.news];
        });
    },
    data() {
      return {
        title: 'Новости',
        news: [],
        page: 1, 
      }
    },
    methods: {
      loadMore () {
        this.page++;
        fetch(`https://domotekhnika.ru/api/v1/news?page=${this.page}`).
        then(response => response.json()).
        then(data => {
          [...data.data.news].forEach(item => {
            this.news.push(item)
          })
        });
      },
      formatDate (date) {
        return new Date(date).toLocaleString('ru', {
                  year: 'numeric',
                  month: 'long',
                  day: 'numeric'
        })
      },
    },
    components: {
      AppCardPreview: CardPreview,
    }
  }
</script>


<style>
  h1{
    font-size: 28px;
    color: rgba(0, 0, 0, 0.8);
    border-bottom: 1px solid #f4f4f4;
    padding-bottom: 8px;
  }
  
  .cards-wrapper{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
    padding: 16px 0;
  }

  .btn {
    display: block;
    background: #fff;
    font-size: 20px;
    letter-spacing: 0.15px;
    color: rgba(0, 0, 0, 0.5);
    border: 1px solid #CCCCCC;
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    padding: 12px 24px;
    cursor: pointer;
    outline: transparent;
    margin: 0 auto;
    margin-top: 32px;
    margin-bottom: 16px;
  }
  .btn:hover {
    box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
  }
  .btn:active {
    border: 1px solid #1f1f1f;
    color: #1f1f1f;
  }
  @media screen and (max-width: 1024px) {
    .cards-wrapper {
      grid-template-columns: 1fr; 
      justify-items: center;
    }
  }
</style>