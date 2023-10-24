<template>
   <div class="product-card">
      <div class="product-card__image">
         <img :src="cardData.imgSrc" alt="product_image" class="product-card__img">
      </div>
      <div class="product-card__content product-content">
         <h2 class="product-content__title">{{ cardData.title }}</h2>
         <div class="product-content__body">
            <div class="product-content__price price-block">
               <div class="price-block__info">
                  Ваша вигода {{ cardData.discount }}₴
               </div>
               <div class="price-block__old-price">{{ cardData.oldPrice }}<span class="fz14">₴</span></div>
               <div class="price-block__current-price">{{ cardData.price }}<span class="fz18">₴</span></div>
            </div>
            <div class="product-content__button">
               <a :href="cardData.link" class="product-content__btn">Купити</a>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
   export default {
      name: 'ProductCard',

      props: {
         cardData: {
            type: Object,
            default: () =>({})
         },
      },
   }
</script>

<style lang="css" scoped>
.product-card {
   border-radius: 8px;
   display: flex;
   gap: 30px;
   padding: 15px;
   position: relative;
   transition: box-shadow 0.3s ease 0s;
}
.product-card:not(:last-child)::after {
   content: '';
   position: absolute;
   bottom: -20px;
   left: 0;
   width: 100%;
   height: 1px;
   background-color: #000;
}
.product-card:hover {
   /* border: 1px solid #000; */
   box-shadow: 0 0 8px #797979;
}
.product-card__image {
   flex: 0 0 320px;
   width: 320px;
   height: 240px;
   overflow: hidden;
}
.product-card__img {
   width: 100%;
   height: 100%;
   object-fit: contain;
}
.product-card__content {
   flex: 0 0 550px;
   display: flex;
   flex-direction: column;
   gap: 30px;
   /* align-items: flex-start; */
}
.product-content__title {
   font-size: 30px;
   font-weight: 500;
   color: rgb(38, 38, 215);
}
.product-content__body {
   display: flex;
   justify-content: space-between;
   /* align-items: flex-end; */
   gap: 20px;
}
.product-content__price {
   text-align: left;
}
.price-block {
   flex: 0 0 auto;
}
.price-block__info {
   color: rgb(63, 54, 54);
   margin-bottom: 30px;
}
.price-block__old-price {
   font-size: 20px;
   color: gray;
   margin-bottom: 10px;
}
.price-block__current-price {
   font-size: 34px;
   color: rgb(246, 41, 26);
   font-weight: 500;
}
.product-content__button {
   flex: 0 0 auto;
   align-self: flex-end;
}
.product-content__btn {
   padding: 10px 20px;
   border-radius: 8px;
   background-color: rgb(59, 145, 59);
   color: #fff;
   font-size: 18px;
   font-weight: 500;
   transition: all 0.3s ease 0s;
}
.product-content__btn:hover {
   background-color: rgb(33, 116, 33);
   box-shadow: 0 0 5px #464545;
}
.fz14 {
   font-size: 14px;
}
.fz18 {
   font-size: 18px;
}
</style>