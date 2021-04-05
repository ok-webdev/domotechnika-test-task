<template>
  <header class="header">
    <p>{{title}}</p>
  </header>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Header',
      }
    }
  }
</script>

<style scoped>
  .header{
    max-width: 1140px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #E8E8E8;
    font-size: 28px;
    font-weight: 400;
    padding: 8px 0;
  }
</style>

