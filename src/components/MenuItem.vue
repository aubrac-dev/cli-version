// ./components/MenuItem.vue

<script>
export default {
	name: 'MenuItem',
    props: {
        imgSrc: String, 
        imgText: String,
        name: String,
        stock: Boolean,
        quantity: Number,
        callf: Function
    },
    mutations: {qV: Number}
}
</script>

<template>
            <!--   <div v-for="item in simpleMenu" :key="item.name" class="menu-item">  v-model.number="quantity" -->
                <div  class="menu-item">
					<img
						class="menu-item__image"
						:src="imgSrc"
						:alt="imgText"
					/>
					<div>
						<h3>{{ name }}</h3>
						<p v-if="stock">En stock</p>
						<p v-else>En rupture de stock</p>
						<div>
							<label for="add-item-quantity"
								>Quantité : {{ quantity }}</label
							>
							<input
								
								id="add-item-quantity"
								type="number"
							/>
							<button @click="callf">
								Ajouter au panier d'achat
							</button>
						</div>
					</div>
                </div>    
        
</template>

<style>
    
    .menu-item {
        display: flex;
        width: 500px;
        justify-content: space-between;
        margin-bottom: 30px;
    }

    .menu-item__image {
        max-width: 300px;
    }

</style>