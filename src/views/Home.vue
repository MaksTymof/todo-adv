<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld/>
    <TodoTask/>
    <DragnDrop/>
    <TestingAdd/>

  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import TodoTask from '@/components/TodoTask.vue'
import DragnDrop from '@/components/DragnDrop.vue'
import TestingAdd from '@/components/TestingAdd.vue'

export default {
  components: {
    HelloWorld,
    TodoTask,
    DragnDrop,
    TestingAdd
  }
}
</script>
<style lang="sass">
.alltodos-container
  display: flex
  justify-content: space-around
  padding: 50px
img
  display: block
  margin: 0 auto
</style>
