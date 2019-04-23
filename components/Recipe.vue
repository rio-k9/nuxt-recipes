<template lang="html">
  <nuxt-link v-bind:to="`/recipes/${id}`">
    <article v-bind:title="title" v-on:click="recipeClick()" class="recipe">
      <div class="thumbnail" v-bind:style="{backgroundImage: `url(${thumbnail})`}">

      </div>
      <h1>{{ title }}</h1>
      <p>{{ previewText}}</p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: ['thumbnail', 'previewText', 'title', 'id'],
  methods: {
    recipeClick() {
      let recipeTitle = this.$el.getAttribute('title');
      console.log(recipeTitle)
    }
  }
}
</script>

<style lang="css" scoped>

.recipe{
  box-sizing:border-box;
  width:280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
  margin:10px;
}
a{
  color:black;
  text-decoration: none;
}
.thumbnail{
  background-position: cover;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>
