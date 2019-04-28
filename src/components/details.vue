<template>
	<div class="details">
		<div class="container">
		  <div class="row">
		    <div class="col-sm">
		      <img :src="form.image" class="img-fluid">
		    </div>
		    <div class="col-sm">
		      <h1>Vinhos</h1>
		      <h1>Nome: {{form.nome}}</h1>
		    </div>
		  </div>
		</div>
	</div>
</template>
<script>
	export default{
		name:'details',
		data(){
			return{
				proId: this.$route.params.Pid,
				title:"details",
				form:{
					nome: '',
					image: '',
				},
				products:[
					{	productTitle:"Sangue de Boi", image       : require('../assets/images/product1.png'), productId:1	},
					{ productTitle:"Moscatell", image       : require('../assets/images/product2.png'), productId:2	},
					{ productTitle:"Casa Daval", image       : require('../assets/images/product3.png'), productId:3 },
					{	productTitle:"Tinto Red",	image       : require('../assets/images/product4.png'), productId:4 },
					{ productTitle:"Canção", image       : require('../assets/images/product5.png'), productId:5 },
					{ productTitle:"Aurora", image       : require('../assets/images/product6.png'), productId:6 },
				]
			}
		},

		mounted(){
			var id_produto = this.proId;
			var titulo = '';
			var img = '';
		  this.products.forEach(function (value, key){
				if(value['productId'] == id_produto){
					titulo = value['productTitle']
					img = value['image']
				}
			})

			this.form.nome = titulo
			this.form.image = img
		}
	}
</script>
