<template>
  <div class="page">
    <products-gallery :list-data="notebooksList"/>
  </div>
</template>

<script>
import ProductsGallery from './components/ProductsGallery.vue';
import { notebooksList } from './constants/3_data_notebooks';

export default {
  name: 'App',
  components: {
    ProductsGallery,
  },
  data() {
    return {
      notebooksList,
    }
  },
}
</script>

<style>
@import url(./assets/reset.css);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.page {
  max-width: 1470px;
  padding: 100px;
  margin: 0 auto;
}
</style>
