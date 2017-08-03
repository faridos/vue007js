<template lang="html">
  <div class="col-md-4">

    <div class="character-card" >
      <div class="card-block">
        <h4 class="card-title">{{item.name}}</h4>
        <div v-for="(value,key,index) in item" >
          <p v-if='index < 5'>
              <strong>{{key}} : </strong> <span>{{value}}</span>
          </p>
        </div>

      </div>
    </div>
    <!-- <button type="button" name="btn btn-success" @click='switchToPreviousItem'>Back To Previous</button> -->
    <button type="button" name="btn btn-success" @click='switchItem'>Switch</button>

  </div>
</template>

<script>
export default {
  props: ['passeditem','type'],
  data(){
    return {
      item: {},
      // previd : null
    }
  },
  methods:{
    switchItem(){

      let random_id=Math.floor(Math.random()* 63) +1
      this.previd=random_id
      fetch(`https://swapi.co/api/${this.type}/${random_id}`,{
        method :'GET'
      })
      .then(response => response.json())
      .then(json => this.item=json)

    },
    // switchToPreviousItem(){
    //   console.log(this.previd)
    //   fetch(`https://swapi.co/api/${this.type}/${this.previd}`,{
    //     method :'GET'
    //   })
    //   .then(response => response.json())
    //   .then(json => this.item=json)
    //
    // },


  }
  ,
  created(){
    this.item=this.passeditem
  }
}
</script>

<style lang="css">
button {
  background-color: green;
}
</style>
