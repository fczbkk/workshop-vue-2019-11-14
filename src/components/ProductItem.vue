<template>
  <wrapper-box>
    <template v-slot:title>{{ productData.title }}</template>
    <div class="productItem">
      <div class="productImage">
        <img :src="imageSource" alt="" height="100">
      </div>
      <p>{{ productData.description }}</p>
      <div class="price">
        {{ productData.price }},- Kč
      </div>
      <div class="addToCart">
        <add-to-cart :productId="productData.id" />
      </div>
    </div>
  </wrapper-box>
</template>

<script>
  import AddToCart from './AddToCart'
  import WrapperBox from './WrapperBox'

  export default {
    components: {
      AddToCart,
      WrapperBox
    },
    props: {
      productData: {
        type: Object,
        required: true
      }
    },
    computed: {
      imageSource () {
        return 'http://localhost:3000/images/' + this.productData.image
      }
    }
  }
</script>

<style scoped>

</style>
