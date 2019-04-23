<template lang="html">
  <header>
    <nav>
      <ul>
        <li><nuxt-link to="/">Starting Page</nuxt-link></li>
        <li><nuxt-link to="/recipes">Recipes</nuxt-link></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
header{
  background:royalblue;
  color:white;
  width:100%;
  height:50px;
  display:flex;
  justify-content:center;
  align-items:center;
}
a{
  color:white;
  text-decoration:none;
}
ul {
  list-style:none;
  padding:0;
  margin:0;
  display:flex;
  justify-content: center;
  align-items: center;
}

li {
  margin: 0 10px;
}
</style>
