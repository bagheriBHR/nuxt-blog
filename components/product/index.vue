<template>
  <div class="mt-3 my-md-2 h-100" dir="rtl">
    <div class="product_item d-flex flex-column justify-content-between">
      <div class="image_bg position-relative d-flex flex-column justify-content-center align-items-center py-3">
        <div v-if="product.discount" class="label_discount">
          {{discount_price}}%
        </div>
        <img :src="require('@/assets/image/' + product.photo)" class="">
        <nuxt-link :to="`/products/${product.slug}`" class="position-absolute btn"> اطلاعات بیشتر</nuxt-link>
      </div>
      <div class="content_bg d-flex flex-column align-items-start px-3 pt-3">
        <h3 class="price mt-1">{{product.price}} تومان</h3>
        <h3 class="name">{{product.name}}</h3>
      </div>
      <div class="content_bg d-flex flex-column align-items-end px-3 pb-3">
        <p class="text-justify my-1">{{product.content}}</p>
        <b-form-rating id="rating-inline" variant="warning" no-border size="sm" inline value="4"></b-form-rating>
      </div>
      </div>
  </div>
</template>

<script>
    export default {
        name: "index",
      data(){
          return{
            discount_price:0,
          }
      },
      props:['product'],
      mounted(){
          this.func1();
      },
      methods:{
          func1:function () {
              this.discount_price =Math.round(Math.abs(((this.product.price - this.product.discount)/this.product.price) * 100));
          }
      }
    }
</script>

<style lang="scss" scoped>
  @media (min-width: 992px) {
    .btn{
      opacity: 0;
    }
  }
  .product_item{
    box-shadow: 0 0 2px rgba(0,0,0,0.2);
    height: 100% !important;
    /*background-color: #FAFAFA;*/
  }
  .image_bg{
    /*background-color:rgba(55, 62, 62, 0.05);*/
  }
  .image_bg img{
    width: 200px;
  }
  .btn{
    bottom: 12px;
    padding: 5px 10px;
    background-color: $orange;
    color: #fff;
    border-radius: 2px;
    font-size: 0.7rem;
    transition: all 0.3s ease-in-out;
    width: 80%;
    font-weight: bold;
  }
  .product_item:hover .btn{
    opacity: 1;
  }
  .content_bg .price{
    font-size: 1rem;
    color: $title;
    font-weight: bold;
  }
  .content_bg .name{
    font-size: 1rem;
    font-weight: bold;
    color: $blue;
  }
  .content_bg .discount{
    font-size: 0.7rem;
    text-decoration: line-through;
    color: red;
  }
  .content_bg p{
    font-size: 0.7rem;
    color: $p;
    line-height: 20px;
  }
  .b-rating{
    background-color: transparent;
    padding: 0px;
  }
  .label_discount{
    color: #fff;
    font-weight: 400;
    font-style: normal;
    padding-right: 0;
    background-color: $orange;
    position: absolute;
    top: 10px;
    left: -6px;
    padding: 1px 7px;
    font-size: 10.844px;
  }
  .label_discount:after{
    border-width: 9px;
    right: -18px;
    top: 0;
    border-style: solid;
    content: "";
    position: absolute;
    border-color: $orange transparent transparent $orange;
  }
  .label_discount:before{
    border-color: #000 #000 transparent transparent;
    border-width: 3px;
    bottom: -6px;
    left: 0;
    border-style: solid;
    content: "";
    position: absolute;
  }
</style>
