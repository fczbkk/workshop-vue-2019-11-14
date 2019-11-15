<template>
  <div class="productsList">
    <product-item
      v-for="(product) in productsList"
      :key="product.id"
      :title="product.title"
      :description="product.description"
      :productData="product"
    />
  </div>
</template>

<script>
  import ProductItem from './ProductItem'
  export default {
    components: {
      ProductItem
    },
    props: {
      productsList: {
        type: Array,
        default () {
          return []
        }
      }
    }
  }
</script>

<style scoped>

</style>
