<template>
  <div class="bg-grey">

    <page-header />
    <back-to-top bottom="10px" right="10px">
      <button type="button" class="btn bg-blue text-white btn-to-top"><i class="fa fa-chevron-up"></i></button>
    </back-to-top>
    <Nuxt />

    <page-footer />

  </div>
</template>

<script>
  import PageHeader from '@/components/header';
  import PageFooter from '@/components/footer';
  import BackToTop from 'vue-backtotop'
  export default {
    components:{
      PageHeader,
      PageFooter,
      BackToTop
    },
  }

</script>

<style>
html {
  font-family: Vazir;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  direction: rtl;
}
body{

}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
.btn-to-top {
  padding: 5px 10px;
  font-size: 15px;
  line-height: 22px;
}
</style>
