<template>
	<div class="details">
		<div class="container">
		  <div class="row">
		    <div class="col-sm">
		      <img :src="form.image" class="img-fluid">
		    </div>
		    <div class="col-sm">
		      <h2>Vinhos</h2>
					<header class="item-title" data-js-item-title>
						<h1 class="item-title__primary ">
							{{form.nome}}
						</h1>
					</header>
					<fieldset class="item-price ">
						<span class="price-tag">
							<span class="price-tag-symbol" content="399.99">R$</span>
							<span class="price-tag-fraction">{{form.valor}}</span>
								</span>
					</fieldset>
					<br>
					<p class="payment-installments free-installments">
						<span data-block="max-installment-recommended-text" class="highlight-info"></span>
						<i class="fab fa-cc-visa"></i>
						<span class="highlight-info" data-block="installments"><span data-block="installmentsQuantity"> {{form.pagamento}} </span></span>
					</p>
					<p class="payment-installments free-installments">
						<span data-block="max-installment-recommended-text" class="highlight-info"></span>
						<i class="fas fa-truck-moving"></i>
						<span class="free-shipping" data-block="no-interest"data-state="visible"> {{form.entrega1}} </span> <br>
						<span class="free-shipping" data-block="no-interest"data-state="visible"> {{form.entrega2}} </span> <br>
					</p>
					<div class="vip-actions-wrapper  vip-actions-wrapper--cart-item">
						<div class="vip-actions item-actions u-clearfix">
							<div class="vip-action-primary">
								<input type="submit" data-js="vip-action-primary" form="productInfo" title="Comprar agora Headphone Sony Xb650bt Com Bluetooth® E Extra Bass" value="Comprar agora" class="btn btn-primary" id="BidButtonTop" tabindex="3">
								<input type="hidden" name="token" value="a2070038f0a088e36dc272715dcd5ed10bc584a52e714548cb7af8f91af5cd06681bf3dd0c1ed0d1c0ebd1f7a6862dcf8f088f34748eaff6e0ac7c7640989d30" />
								<input type="submit" data-js="vip-action-cart" title="Adicionar ao carrinho Headphone Sony Xb650bt Com Bluetooth® E Extra Bass" value="Adicionar ao carrinho" class="btn btn-primary" tabindex="4" formaction="https://www.mercadolivre.com.br/gz/cart/item/add?noindex=true">
							</div>
					  </div>
					</div>
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
					valor: '',
					pagamento: '',
					entrega1: '',
					entrega2: '',
				},
				products:[
					{	productTitle:"Sangue de Boi", image : require('../assets/images/product1.png'), productId:1, valor: '75,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 10 dias.', pagamento: '12x R$ 6,25‬ sem juros com seu VISA'	},
					{ productTitle:"Moscatell", image : require('../assets/images/product2.png'), productId:2 , valor: '60,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 7 dias.', pagamento: '12x R$ 5,00 sem juros com seu VISA'	},
					{ productTitle:"Casa Daval", image : require('../assets/images/product3.png'), productId:3, valor: '55,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 8 dias.', pagamento: '12x R$ 4,58 sem juros com seu VISA'	},
					{	productTitle:"Tinto Red",	image : require('../assets/images/product4.png'), productId:4, valor: '93,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 13 dias.', pagamento: '12x R$ 7,75 sem juros com seu VISA'	},
					{ productTitle:"Canção", image : require('../assets/images/product5.png'), productId:5 , valor: '88,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 12 dias.', pagamento: '12x R$ 7,33 sem juros com seu VISA'	},
					{ productTitle:"Aurora", image : require('../assets/images/product6.png'), productId:6 , valor: '115,00', entrega1:'Envio R$ 39,76 Chegará' , entrega2: 'em 11 dias.', pagamento: '12x R$ 9,33 sem juros com seu VISA'	},
				]
			}
		},

		mounted(){
			var id_produto = this.proId;
			var titulo = '';
			var img = '';
			var valor = '';
			var entrega1 = '';
			var entrega2 = '';
			var pagamento = '';
		  this.products.forEach(function (value, key){
				if(value['productId'] == id_produto){
					titulo = value['productTitle']
					img = value['image']
					valor = value['valor']
					entrega1 = value['entrega1']
					entrega2 = value['entrega2']
					pagamento = value['pagamento']
				}
			})

			this.form.nome = titulo
			this.form.image = img
			this.form.valor = valor
			this.form.entrega1 = entrega1
			this.form.entrega2 = entrega2
			this.form.pagamento = pagamento
		}
	}
</script>
