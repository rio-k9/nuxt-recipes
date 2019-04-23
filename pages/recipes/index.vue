<template lang="html">
  <section class="recipes">
    <Recipe
    v-for="recipe in recipes"
    v-bind:key="recipe.id"
    v-bind:thumbnail="recipe.thumbnail"
    v-bind:title="recipe.title"
    v-bind:id="21"
    v-bind:previewText="recipe.previewText"
    />
  </section>
</template>
<!-- Components only required if they have their own methods / databinding -->
<script>
import Recipe from '~/components/Recipe';
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes: [
            {
              id: "21",
              title: "Delicious Pizza",
              previewText: "Awesome Pizza!",
              thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/how_to_make_pizza_50967_16x9.jpg"
            },
            {
              id: "22",
              title: "Buff Lasagna",
              previewText: "Nice Lasagna",
              thumbnail: "https://img1.southernliving.timeinc.net/sites/default/files/styles/medium_2x/public/image/2018/11/main/gettyimages-998672040.jpg"
            }
          ]
        })
      }, 1000) //Simulate Promise FETCH of MicroService Data
    })
  }
}
</script>

<style lang="css" scoped>
.recipes{
  display:flex;
  flex-flow: row wrap;
  justify-content: center;
  align-items: center;
}
</style>
