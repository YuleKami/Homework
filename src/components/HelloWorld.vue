<template>
    <div class="nav-bar"></div>

    <div class="cart">
        <p>Cart {{ cart }}</p>
    </div>


    <div class="product-display">
        <div class="product-container">
            <div class="product-image">
                <img :src="image">
                <p v-if="inStock">In Stock</p>
                <p v-else :class="{ textLineThrough: !inStock }">Out of Stock</p>
            </div>


            <div class="product-info">
                <h1>{{ product }}</h1>

                <div style="display: inline-block; padding: 2em">
                    <div v-for="variant in variants" :key="variant.id">
                        <p @mouseover="updateProduct(variant.image)">
                            {{ variant.color }}
                        </p>
                    </div>
                </div>

                <div style="display: inline-block; padding: 2em">
                    <ul v-for="size in sizes" :key="size.sizeId">
                        <li>{{ size }}</li>
                    </ul>
                </div>

                <div style="display: inline-block; padding: 2em">

                    <div v-for="detail in details" :key="detail.detailId">
                        {{ detail }}
                    </div>
                </div>

                <p>{{ description }}</p>
                <a :href="link">More products like this</a>

                <div style="padding: 1em">
                    <!--                <span v-if="inSale">Купить по скидке: {{ sale }}</span>-->
                    <!--                <span v-else>Купить</span>-->
                    <button v-on:click="addToCart" :disabled="!inStock" :class="{ disabledButton: !inStock }">
                        Add to cart
                    </button>
                    <button @click="removeFromCart">Убрать из корзину</button>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'App',
        components: {},
        data() {
            return {
                product: 'Socks',
                description: 'A pair of warm fuzzy socks',
                //image: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
                image: " https://www.vuemastery.com/images/challenges/vmSocks-blue-onWhite.jpg",
                details: ['50% cotton', '30% wool', '20% polyester'],
                sizes: ['S', 'M', 'L', 'XL'],
                variants: [
                    {
                        id: 2234,
                        color: "green",
                        image: " https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg",
                    },
                    {
                        id: 2235,
                        color: "blue",
                        image: "https://www.vuemastery.com/images/challenges/vmSocks-blue-onWhite.jpg",
                    },
                ],
                altText: 'A pair of socks',
                link: 'https://www.amazon.com/s/ref=nb_sb_noss?url=search-alias%3Daps&field-keywords=socks.',
                inStock: false,
                inSale: true,
                sale: '50%',
                cart: 0,
            };
        },
        methods: {
            addToCart() {
                this.cart += 1
            },
            removeFromCart() {
                this.cart -= 1
            },

            updateProduct(variantImage) {
                this.image = variantImage
            },

        },
    };

</script>

<style scoped>

</style>
