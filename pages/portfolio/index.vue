<template>
  <div class="bg-gray col-12 px-2 px-md-5 py-4">
    <div class="customShadow d-flex flex-column bg-white p-4 ">
      <Title title="نمونه کارها"/>
      <div class="d-flex flex-wrap mb-4">
        <div class="col-12 col-md-3 mt-4" v-for="item in portfolio" :key="item.id">
          <portfolioCarousel :title="item.title" :photos="item.photos" :date="item.date"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
    import portfolioCarousel from '@/components/portfolioCarousel'
    import Title from '@/components/title'
    export default {
        name: "index",
        data(){
          return{
            portfolio: [
              {
                id:'1',
                title: 'تعمیر شوفاژ',
                photos:['service42.jpg','service4.jpg'],
                date:'3/4/99'
              },
              {
                id:'2',
                title: 'حفر چاه',
                photos:['service32.jpg','service3.jpg'],
                date:'3/4/99'
              },
              {
                id:'3',
                title: 'لوله کشی ساختمان',
                photos:['service22.jpg','service2.jpg'],
                date:'3/4/99'
              },
              {
                id:'4',
                title: 'تعمیر موتور',
                photos:['service12.jpg','service1.jpg'],
                date:'3/4/99'
              },
              {
                id:'5',
                title: 'تعمیر شوفاژ',
                photos:['service42.jpg','service4.jpg'],
                date:'3/4/99'
              },
              {
                id:'6',
                title: 'حفر چاه',
                photos:['service32.jpg','service3.jpg'],
                date:'3/4/99'
              },
              {
                id:'7',
                title: 'لوله کشی ساختمان',
                photos:['service22.jpg','service2.jpg'],
                date:'3/4/99'
              },
              {
                id:'8',
                title: 'تعمیر موتور',
                photos:['service12.jpg','service1.jpg'],
                date:'3/4/99'
              },
            ],
          }
        },
      components:{
        portfolioCarousel,
        Title
      }
    }
</script>

<style scoped>

</style>
