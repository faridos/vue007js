<template lang="html">
  <div class="col-md-12">
    <Item
     v-for ="(itemm,index) in items"
      key='index'
      :passeditem='itemm'
      :type='typee'
     />
  </div>
</template>

<script>
import Item from './Item.vue'
export default {
  data(){
    return {
      typee: this.$route.params.type,
      items: []
    }
  },
  watch:{
  '$route': 'fetchItems'
  },
  methods: {
    fetchItems() {
      this.items=[]
      this.type=this.$route.params.type
      let initial_ids=[1,3,4]
      for(let i in initial_ids){

       let  id=initial_ids[i]
       
        fetch(`https://swapi.co/api/${this.type}/${id}`,
        {method:'GET'})
        .then(response =>response.json())
        .then(json => this.items.push(json))
      }

    }
},
created(){
  this.fetchItems()
},
components: {
  Item
}
}
</script>

<style lang="css">
</style>
