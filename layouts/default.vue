<template>
  <div class="bg-grey">

    <page-header />

    <Nuxt />

    <page-footer />

  </div>
</template>

<script>
  import PageHeader from '@/components/header';
  import PageFooter from '@/components/footer';

  export default {
    components:{
      PageHeader,
      PageFooter,
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
</style>
