<template>
  <div class="home">
    <h1>{{title}}</h1>
          <h2>Why Us ?</h2>
          {{why}}
<div class="row">
  
</div>
    <div class="row">

      <div class="col-md-4 col-lg4" v-for="(data,index) in products" :key="index"> Front-End
        <img :src="data.image" class="img-fluid">
         <h3 @click="goTodetail(data.productId)" >{{data.productTitle}}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      title: 'Welcome To Dev Lender ',
      why: 'because blah blah blah',
      products:[
      {
        productTitle:"for more details click here",
        image       : require('../assets/images/product.jpg'),
        productId:1
      },
      
      ]
    }
  },
  methods:{
  goTodetail(prodId) {
    let proId=prodId
    this.$router.push({name:'details',params:{Pid:proId}})
  }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.row img{
  max-height: 15em;
  width: 100%;

}
.row h3{
  cursor:pointer;
}
</style>
