<template>
  <div class="sidebar d-flex flex-column align-items-start p-1 bg-white h-100">
    <h4 class="w-100  pb-2 pr-3 pt-4 text-right">{{title}}</h4>
    <div class="d-flex flex-column align-item-start w-100">

      <div v-if="category">
        <b-card no-body class="mb-1" v-for="item in category" :key="item.name">
          <b-card-header header-tag="header" class="p-1" role="tab">
            <b-button block v-b-toggle="'accordion-'+item.name" variant="white">{{item.name}}</b-button>
          </b-card-header>
          <b-collapse :id="'accordion-'+item.name" accordion="my-accordion" role="tabpanel">
            <b-card-body>
              <b-card-text>
                <ul class="pr-1">
                  <li v-for="subItem in item.subCategory" :key="subItem"><button @click="subItemClicked(subItem)"> {{subItem}}</button></li>
                </ul>
              </b-card-text>
            </b-card-body>
          </b-collapse>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
      name: "index",
      props:['title','category','attributeGroup'],
      methods:{
        subItemClicked(subItemName){
          this.$emit('subItemClicked',subItemName)
        }
      }
    }
</script>

<style lang="scss" scoped>
  .card-header{
    background-color: transparent;
    border: none !important;
  }
  .card-body{
    padding-top: 0px;
    padding-bottom: 0px;
  }
  .card{
    border: none !important;
  }
  .btn{
    color: $title;
    text-align: right;
    font-size: 0.8rem;
    font-weight: bold;
  }
  .btn:focus{
    outline: none !important;
    border: none !important;
    box-shadow: none !important;
  }
  .sidebar{
    border: 1px solid #e0e0e0;
    box-shadow: 0 0 10px rgb(236, 236, 236);
  }
  .sidebar h4{
    font-size: 0.9rem;
    border-bottom: 1px solid #e0e0e0 !important;
    color: rgb(121, 121, 121);
  }
  .sidebar h5{
    font-size: 0.9rem;
    color:rgb(112, 112, 112)
  }
  .sidebar ul li{
    list-style-type: none;
    text-align: right;
    padding: 5px 0;
  }
  .sidebar ul li button{
    border: none !important;
    outline: none !important;
    box-shadow: none !important;
    background-color: transparent;
    color: rgb(144, 144, 144);
    font-size: 0.8rem;
  }
</style>
