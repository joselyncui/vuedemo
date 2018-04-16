<template>
  <div id="item-container">
    <input type="checkbox" v-model="isComplate"/>
    <div v-if="item" v-bind:class="{complated:item.isComplate}">{{item.title}}</div>
    <span type="button" class="del" @click="del_item()">delete</span>
  </div>
</template>

<script>

  export default {
    props:["item","operate"],

    data:function(){
      return {
        isComplate:false,
      }
    },

    methods:{
      del_item:function(){
        this.$emit('remove');
      },

    },
    // watch:{
    //   isComplate:function(val){
    //     if(val){
    //
    //     }
    //   },
    // },

  }
</script>

<style scoped>
  #item-container{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    height:3em;
    border-bottom: gray solid 0.4px;
    width:80%;
    margin:0 auto;

  }
  .del{
    width:4em;
    height:1.2em;
    line-height: 1.2em;
    border:gray solid 1px;
    border-radius: 1em;
    margin-left: 1.2em;
  }

  .complated{
    text-decoration:line-through;
  }
</style>
