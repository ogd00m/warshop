<template>
    <div class='v-catalog'>
        <h1>Catalog</h1>
        <div class="v-catalog__list">
        <v-catalog-item
            v-for="product in products"
            :key="product.article"
            v-bind:product_data="product"
            @sendDataToParent="showChildArticleInConsole"
         />
        </div>
    </div>
    
</template>

<script>
    import vCatalogItem from './v-catalog-item.vue'

export default {
    name: "v-catalog",
    components: {
        vCatalogItem,
    },
    props: {},
    data() {
        return{
            products: [
    {
      image: "1.jpg",
      name: "T-shirt 1",
      price: 3000,
      article: "T1",
      available: true,
      category: "Мужские"
    },
    {
      image: "2.jpg",
      name: "T-shirt 2",
      price: 3000,
      article: "T2",
      available: true,
      category: "Женские"
    },
    {
      image: "3.jpg",
      name: "T-shirt 3",
      price: 3000,
      article: "T3",
      available: false,
      category: "Женские"
    },
    {
      image: "4.jpg",
      name: "T-shirt 4",
      price: 3000,
      article: "T4",
      available: true,
      category: "Мужские"
    },
    {
      image: "5.jpg",
      name: "T-shirt 5",
      price: 3000,
      article: "T5",
      available: false,
      category: "Женские"
    },
    {
      image: "6.jpg",
      name: "T-shirt 6",
      price: 3000,
      article: "T6",
      available: true,
      category: "Женские"
    }
  ]
        }
    },
    computed: {},
    methods: {
      showChildArticleInConsole (data) {
        console.log(data)
      }
    }
}
</script>
<style lang="scss">
    .v-catalog {
        &__list {
            font-family: 'Roboto', sans-serif;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }
    }
</style>