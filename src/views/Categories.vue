<template>
  <div>
    <h1>Categories</h1>

    <wrapper-box>
      <template v-slot:title>
        List of <em>categories</em>
      </template>
      <ul>
        <li
          v-for="(category, categoryId) in categoriesList"
          :key="categoryId"
        >
          <router-link
            :to="{name: 'category', params: {category_id: categoryId}}"
          >{{ category }}
          </router-link>
        </li>
      </ul>
    </wrapper-box>
  </div>
</template>

<script>

  import WrapperBox from '../components/WrapperBox'

  export default {
    components: { WrapperBox },
    data () {
      return {
        categoriesList: {}
      }
    },
    mounted () {
      fetch('http://localhost:3000/categories')
        .then((response) => response.json())
        .then((data) => this.categoriesList = data)
    }
  }
</script>

<style scoped>

</style>
