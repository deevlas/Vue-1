<template>
  <div id="todo">
    <div v-if="toDoArr.length < 10">
      <input type="text" placeholder="Input ToDo" v-model="inpTxt">
      <button @click="addToDo">Add ToDo</button>
    </div>
    <ul>
      <li v-for="(toDo, y) in toDoArr" :key="y">
        {{toDo}}
        <button @click="delToDo(y)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "ToDo",
    data() {
      return {
        inpTxt: "",
        toDoArr: []
      }
    },
    methods: {
      addToDo() {
        if(this.inpTxt.length > 0) {
          this.toDoArr.push(this.inpTxt)
          this.inpTxt = ""
        }
      },
      delToDo(i) {
        this.toDoArr.splice(i, 1)
      }
    }
  }
</script>

<style>

</style>