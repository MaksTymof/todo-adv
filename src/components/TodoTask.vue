<template lang="pug">
    .container-todo
        
        label(for="title") Enter the task
          input(type="text" name="title" v-model="title")
        label(for="listNumber") Enter list number
          input(type="text" name="listNumber" v-model="listNumber")
        label(for="taskId") Enter task id
          input(type="text" name="taskId" v-model="taskId")
        button(@click="addTodo()") Add Todo
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

<style lang="sass">
form
  text-align: center
label
  color: #fff
  padding: 20px
input
  padding: 10px
  margin: 15px 15px
  width: 35%
  border: none
  border-radius: 15px
button
  padding: 15px
  background-color: #808080
  color: #fff
  font-size: 18px
  margin-top: 20px
  border: none
  border-radius: 15px
</style>
