<template>
    <div class="col-12 col-md-3 d-flex flex-column align-items-start mt-5">
      <div class="image_container position-relative">
        <img :src="require('@/assets/image/' + employee.photo)" class="w-100">
        <div class="hover d-flex align-items-center justify-content-center h-100 w-100 position-absolute">
          <div v-for="item in employee.socials">
            <a v-b-tooltip.hover :title="item.value">
              <div class="follow mx-1">
                <i :class="'fa fa-'+item.name"></i>
              </div>
            </a>
          </div>
        </div>
      </div>
      <h6 class="mt-3">{{employee.name}}</h6>
      <span>{{employee.post}}</span>
    </div>
</template>

<script>
    export default {
        name: "index",
        props:['employee']
    }
</script>

<style lang="scss" scoped>
  .image_container{
    box-shadow: 0 0 5px rgba(0,0,0,0.2);
    border-radius: 3px;
    overflow: hidden;
    cursor: pointer;
  }
  .image_container:hover .hover{
    opacity: 1;
  }
  .image_container img{

  }
  h6{
    font-size: 0.9rem;
    font-weight: bold;
    color: #413d77;
  }
  span{
    font-size: 0.8rem;
    color: $title;
    font-weight: bold;
  }
  .hover{
    background-color: rgba(65,61,119,0.7);
    top: 0;
    left: 0;
    opacity: 0;
    transition: all 0.3s ease-in-out;
  }
  .follow{
    width: 30px;
    height: 30px;
    border-radius: 2px;
    background-color: rgba(255,255,255,0.2);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  @media (max-width: 600px) {
    .hover{
      opacity: 1;
    }
  }
</style>
<style>
  .tooltip-inner {
    color: #fff;
    background-color: rgba(255,255,255,0.2) !important;
    border-radius: 2px;
  }
  .bs-tooltip-top .arrow::before, .bs-tooltip-auto[x-placement^="top"] .arrow::before {
    border-top-color: rgba(255,255,255,0.2)  !important;
  }

</style>
