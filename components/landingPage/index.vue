<template>
  <div class="d-none d-md-block">
    <div class="d-flex mx-5 mt-4">
      <div class="col-8 p-0 d-flex">
        <div class="col-9 p-0">
          <landingPageCarousel />
<!--          <img src="@/assets/img/carousel6.jpg" class="w-100">-->
        </div>
        <div class="col-3 d-flex flex-column justify-content-between h-100">
          <div class="col px-0">
            <pic-item title="تعمیر شوفاژ خانه" image="carousel1.jpg" body="لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از چاپ و بو لورم" />
          </div>
          <div class="col px-0 pt-2">
            <pic-item title="لوله کشی آب" image="carousel2.jpg" body="لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از چاپ و بو لورم" />
          </div>
          <div class="col px-0 pt-2">
            <pic-item title="تعمیر شوفاژ خانه" image="carousel3.jpg" body="لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از چاپ و بو لورم" />
          </div>
        </div>
      </div>
      <div class="col-4 d-flex flex-column justify-content-between p-0">
        <div style="height: 68%">
          <pic-item title="تعمیر شوفاژ خانه" image="carousel4.jpg" body="لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از چاپ و بو لورم" />
        </div>
        <div class="mt-2" style="height: 32%">
          <pic-item title="دفتر کار" image="carousel5.jpg" body="لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از چاپ و بو لورم" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
    import PicItem from './picItem'
    import landingPageCarousel from './landingPageCarousel'
    export default {
      name: "index",
      components:{
          PicItem,
          landingPageCarousel
      }
    }
</script>

<style lang="scss" scoped>
</style>
