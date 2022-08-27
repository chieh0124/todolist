<!-- Use preprocessors via the lang attribute! e.g. <template lang="pug"> -->
<template>
<div id="topic">
  <t1>Todo-list</t1>
  </div>
  <div id="app">
     <input v-model="inputVal"/>
     <button @click="addItem()">＋</button>
     <ul class="horizon" v-for="(item,index) in todoList">
       <li class="item-name">
         {{item}}
       </li>
       <span class="item-del" @click="removeItem(index)"> x </span>
     </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      todoList: ["brushing teeth after each meal","stay healthy"],
      inputVal: ""
    };
  },
  methods: {
    addItem() {
      if(this.inputVal.length < 1) return
      this.todoList.push(this.inputVal)
      this.inputVal = ""
    },
    removeItem(index) {
      this.todoList.splice(index, 1)
    }
  }
};
</script>

git add .
git commit -m "project todo"


<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#topic {
  font-family:'Courier New', Courier, monospace;
  color: navy;
  margin-top: 60px;
}
.horizon{
  display:flex;    
}
.item-name {
    
}
.item-del {
  padding: 0px 10px;
  cursor: pointer;
}

</style>