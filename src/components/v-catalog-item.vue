<template>
  <div class="v-catalog-item">
      <img class="v-catalog-item__img" :src=" require('../assets/images/' + product_data.image)" alt="img">
      <p class="v-catalog-item__name">{{product_data.name}}</p>
      <p class="v-catalog-item__price">Price: {{product_data.price.toFixed(2)}} грн</p>
      <button 
            class="v-catalog-item__add_to_cart_btn btn" 
            @click.prevent="sendDataToParent"
            > Add to cart </button>
  </div>
</template>

<script>
export default {
    name: "v-catalog-item",
    props: {
        product_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return {}
    },
    computed: {},
    methods: {
        sendDataToParent() {
            this.$emit('sendDataToParent', this.product_data.article)
        }
    }
}
</script>

<style lang="scss">
    .v-catalog-item {
        flex-basis: 25%;
        box-shadow: 0 0 8px #e0e0e0;
        padding: $padding*2;
        margin-bottom: $padding*2;
        &__img {
            max-width: 100px;
        }
    }
</style>