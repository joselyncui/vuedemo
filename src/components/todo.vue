<template>
  <div id="todo-container">
    <CHeader></CHeader>

    <div id="content">
      <input type="text" placeholder="please input todo" @keyup.enter="submit" v-model="todo"/>
      <Item v-for="(item,index) in items" :key="item.id" v-bind:item="item"
            v-on:remove="rem_todo(index)" v-on:complate="comp_todo(index)"/>
      <Tabs />
    </div>
    <CFooter></CFooter>

  </div>
</template>

<script>

  import CHeader from './header'
  import CFooter from './footer'
  import Tabs from './tabs'
  import Item from './item'


  export default {
    name:'ToDo',
    components:{
      CHeader,
      CFooter,
      Tabs,
      Item,
    },
    data:function(){
      return {
        todo:'',
        items:[],
      }
    },
    methods:{
      submit:function(){
        this.items.push({id:this.items.length,title:this.todo,isComplate:false})
      },
      rem_todo:function(index){
        this.items.splice(index,1);
      },
      comp_todo:function(index){
        this.items[index].isComplate = true;
      }
    }
  }

</script>

<style scoped>

  #content{
    background: white;
    width:80%;
    height:auto;
    margin:0 auto;
    display: flex;
    flex-direction: column;
    -webkit-flex-direction: column;
    -ms-flex-direction: column;
    padding: 3em;
  }
  input[type=text]{
    width:80%;
    height:3em;
    font-size: 1em;
    color: lightslategrey;
    border: darkgray 1px solid;
    border-radius: 0.5em;
    align-self: center;
    padding:0.2em;
  }

  input:focus{
    border: darkgray 1px solid;
    border-radius: 0.5em;
    outline: none;
  }

</style>
