<template>
  <div class="home">
    <h1>Vinícula "E vinhos"</h1>
    <img src="http://www.marcelocopello.com/imagem/870/580/0/1/2193/870x580xLondres-dicas-de-lojas-de-vinhos.jpeg.pagespeed.ic.0110i_pDCr.jpg" alt="Italian Trulli">
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      title: 'Vinhos a Venda',
      products:[
      {
        productTitle:"Sangue de Boi",
        image       : require('../assets/images/product1.png'),
        productId:1
      },
      {
        productTitle:"Moscatell",
        image       : require('../assets/images/product2.png'),
        productId:2
      },
      {
        productTitle:"Casa Daval",
        image       : require('../assets/images/product3.png'),
        productId:3
      },
      {
        productTitle:"Tinto Red",
        image       : require('../assets/images/product4.png'),
        productId:4
      },
      {
        productTitle:"Canção",
        image       : require('../assets/images/product5.png'),
        productId:5
      },
      {
        productTitle:"Aurora",
        image       : require('../assets/images/product6.png'),
        productId:6
      }
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
