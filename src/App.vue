<template>
  <div id="app">
    <app-header />
    <router-view />
    <app-footer />
  </div>
</template>

<script>
  import Header from '@/components/AppHeader'
  import Footer from '@/components/AppFooter'
  export default {
    components: {
      AppHeader: Header,
      AppFooter: Footer,
    }
  }
</script>

<style>
  *,
  *::before,
  *::after {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .main{
     min-height: calc(100vh - 96px);
  }
</style>
