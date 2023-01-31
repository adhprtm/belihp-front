<template>
    <div v-if="products.length > 0">
    <ProductListItem
        v-for="product in products"
        :key="product.id"
        :product="product" />
    </div>
    <p v-else>Keranjang Anda Kosong!</p>
</template>

<script>
import ProductListItem from './ProductListItem.vue';
export default{
    name: 'ProductsList',
    props: ['products'],
    components: {
        ProductListItem,
    },
}
</script>