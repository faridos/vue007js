<template lang="html">
  <div id='app'>
<h3>Star Base router</h3>
<h4>
 <!--<router-link :to="{ name: '', params: {} }"></router-link>-->
 <router-link class="link" to="/data/people">Meet the charracters</router-link> |
 <router-link class="link" to="/data/planets">explore the Planets</router-link>
</h4>
<router-view></router-view>
  </div>
</template>

<script>
export default {


}
</script>

<style lang="css">
.link, .link:hover{
  color : #4FC08D
}
</style>
