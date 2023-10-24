<template>
   <div class="products-gallery">
      <product-card v-for="card in listData" :key="card.id" :card-data="card" />
   </div>
</template>

<script>
import ProductCard from './ProductCard.vue';

export default {
   name: 'ProductsGallery',
   props: {
      listData: {
         type: Array,
         default: () => []
      },
   },
   components: { ProductCard }
}
</script>

<style lang="css" scoped>
.products-gallery {
   width: 930px;
   display: grid;
   gap: 40px;
   margin: 0 auto;
}
</style>