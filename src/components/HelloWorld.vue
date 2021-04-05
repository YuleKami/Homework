<template>
  <div class="nav-bar"></div>

  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img :src="image">
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>

      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
        <ul v-for="variant in variants" :key="variant.variantId">
          <li>{{variant.color}}</li>
        </ul>
        <ul v-for="size in sizes" :key="size.sizeId">
          <li>{{size}}</li>
        </ul>
        <div v-for="detail in details" :key="detail.detailId">{{detail}}</div>
        <span v-if="inSale">Купить по скидке: {{sale}}</span>
        <span v-else>Купить</span>
        <p>{{ description }}</p>
        <a :href="link">More products like this</a>

      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'App',
    components: {
    },
    data() {
      return {
        product: 'Socks',
        description: 'A pair of warm fuzzy socks',
        //image: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
        image: " https://www.vuemastery.com/images/challenges/vmSocks-blue-onWhite.jpg",
        details: ['50% cotton', '30% wool', '20% polyester'],
        sizes: ['S','M', 'L', 'XL'],
        variants: [
          {
            id: 2234,
            color: 'green'
          },
          {
            id: 2235,
            color: 'blue'
          }
        ],
        altText: 'A pair of socks',
        link: 'https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=socks.',
        inStock: true,
        inSale: true,
        sale: '50%',
      };
    },
  };

</script>


<style scoped>

</style>
