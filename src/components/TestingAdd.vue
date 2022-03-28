<template lang="pug">
  .my-container
    label(for="title") Enter the task
      input(type="text" name="title" v-model="title")
    label(for="listNumber") Enter list number
      input(type="text" name="listNumber" v-model="listNumber")
    label(for="taskId") Enter task id
      input(type="text" name="taskId" v-model="taskId")
    button(@click="addTodo()") Add Todo
    .listTodos
      ul
        li(v-for="(item, idx) in items" :key="item.idx")
          p  id {{ item.id }}
          p  title {{ item.title }}
          p  List {{ item.list }}
</template>

<script>
export default {
  data () {
    return {
      title:"",
      listNumber:"",
      taskId:"",
      items: [
      {
        id: 0,
        title: 'sleeping',
        list: 1
      },
      {
        id: 1,
        title: 'eating',
        list: 1
      },
      {
        id: 2,
        title: 'reading',
        list: 2
      },
      {
        id: 3,
        title: 'meeting',
        list: 1
      },
      {
        id: 4,
        title: 'running',
        list: 1
      },
      {
        id: 5,
        title: 'go to the gym',
        list: 3
      },
      {
        id: 6,
        title: 'swimming',
        list: 3
      }]
    }
  },
  methods: {
    addTodo: function () {
      console.log("hello")
      if (this.title && this.listNumber && this.taskId) {
        this.items.push({id: this.taskId, title: this.title, list: this.listNumber})
        return console.log(this.items[7])
      }
    }
  }
}
</script>

<style lang="css">
.my-container{
    display: block;
    color: #fff;
  }
li{
  border: 2px solid #fff;
  list-style: none;
  width: 35%;
  margin: 5px auto;
  padding-left: 15px;
}
</style>
