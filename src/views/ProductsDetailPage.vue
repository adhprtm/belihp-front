<template>
    <div id="page-wrap" v-if="product">
        <div id="img-wrap">
            <img v-bind:src="product.imageUrl" />
        </div>
        <div id="product-details">
            <h1>{{ product.name }}</h1>
            <h3 id="price">Rp{{ product.price }}</h3>
            <p>Ulasan: {{ product.averageRating }}</p>
            <button id="add-to-cart">Tambahkan Ke Keranjang</button>
            <h4>Deskripsi Produk</h4>
            <p>{{ product.description }}</p>
        </div>
    </div>
    <NotFoundPage v-else />
</template>

<script>
import { products  } from '..//importdata.js';
import NotFoundPage from './NotFoundPage.vue';

export default {
    name : 'ProductsDetailPage',
    components: {
      NotFoundPage,
    },
    data() {
        return {
            product: products.find((p)=> p.id === this.$route.params.id),
        };
    }
}
</script>

<style scoped>
  #page-wrap {
    margin-top: 16px;
    padding: 16px;
    max-width: 600px;
  }

  #img-wrap {
    text-align: center;
  }

  img {
    width: 400px;
  }

  #product-details {
    padding: 16px;
    position: relative;
  }

  #add-to-cart {
    width: 100%;
  }

  #price {
    position: absolute;
    top: 24px;
    right: 16px;
  }
</style>
