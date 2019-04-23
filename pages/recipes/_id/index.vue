<template lang="html">
  <section v-on:click="infoClick()" class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div class="">
      <img v-bind:src="recipe.thumbnail" v-bind:alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>
<!-- IF YOU ARE BINDING AN ATTRIBUTE FROM JAVASCRIPT DATA, USE V-BIND:ATTRNAME -->
<script>
export default {

  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "21",
              title: "Delicious Pizza",
              previewText: "Awesome Pizza!",
              descriptionText: "This is really a delicious meal!",
              thumbnail: "https://ichef.bbci.co.uk/food/ic/food_16x9_832/recipes/how_to_make_pizza_50967_16x9.jpg"
            },
            {
              id: "22",
              title: "Buff Lasagna",
              previewText: "Nice Lasagna",
              descriptionText: "This is really a delicious meal!",
              thumbnail: "https://img1.southernliving.timeinc.net/sites/default/files/styles/medium_2x/public/image/2018/11/main/gettyimages-998672040.jpg"
            }
          ].find((el) => {
            return el.id === context.params.id
          })
        })
      }, 1000)
    })
  }
}
</script>

<style lang="css" scoped>
.single-recipe {
  display:flex;
  justify-content: center;
  align-items: center;
  text-align:center;
  padding:30px;
  flex-flow:column nowrap;
}
</style>
