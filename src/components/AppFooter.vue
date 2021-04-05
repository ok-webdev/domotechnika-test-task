<template>
  <footer class="footer">
    <p>{{title}}</p>
  </footer>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Footer',
      }
    }
  }
</script>

<style scoped>
  .footer{
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