<template lang="html">
  <div class="" id="app">

      <h3>{{title}}</h3>
      <div class="row">
        <!--<character v-bind:id='1'/>-->
          <character v-for='(id,index) in initial_ids'
          :id='id'
          key='index'
          />

      </div>

  </div>
</template>

<script>
import  Character from './components/Character.vue'

export default {

  name:'app',
  data(){
    return {
      title:'Generate your team',
      initial_ids:[1,2,3]
    }
  },
 components:{
  Character
  }

}
</script>

<style lang="css">
</style>
