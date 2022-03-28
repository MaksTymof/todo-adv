<template lang="html">
  <div class="container">
    <div class="container-item">
      <h1> Todos </h1>
        <div
            class='drop-zone'
            @drop='onDrop($event, 1)'
            @dragover.prevent
            @dragenter.prevent
            >
            <div
                v-for='item in listOne'
                :key='item.title'
                class='drag-el'
                draggable
                @dragstart='startDrag($event, item)'
                >
              {{ item.title }}
            </div>
      </div>
    </div>
    <div class="container-item">
      <h1> Done Todos </h1>
      <div
          class='drop-zone'
          @drop='onDrop($event, 2)'
          @dragover.prevent
          @dragenter.prevent
          >
        <div
          v-for='item in listTwo'
          :key='item.title'
          class='drag-el'
          draggable
          @dragstart='startDrag($event, item)'
          >
          {{ item.title }}
        </div>
      </div>
    </div>
    <div class="container-item">
      <h1>Delayed Todos</h1>
      <div
          class='drop-zone'
          @drop='onDrop($event, 3)'
          @dragover.prevent
          @dragenter.prevent
          >
        <div
          v-for='item in listThree'
          :key='item.title'
          class='drag-el'
          draggable
          @dragstart='startDrag($event, item)'
          >
          {{ item.title }}
        </div>
      </div>
   </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
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
  computed: {
    listOne () {
      return this.items.filter(item => item.list === 1)
    },
    listTwo () {
      return this.items.filter(item => item.list === 2)
    },
    listThree () {
      return this.items.filter(item => item.list === 3)
    }
  },
  methods: {
    startDrag: (evt, item) => {
      evt.dataTransfer.dropEffect = 'move'
      evt.dataTransfer.effectAllowed = 'move'
      evt.dataTransfer.setData('itemID', item.id)
    },
    onDrop (evt, list) {
      const itemID = evt.dataTransfer.getData('itemID')
      const item = this.items.find(item => item.id == itemID)
      item.list = list
    }
  }
}
</script>

<style lang="sass">
.container
    display: flex
    justify-content: space-around
.container-item
  width: 30%
  h1
    color: #fff
.drop-zone
    width: 100%
    background-color: #808080
    margin-bottom: 10px
    padding: 10px
    min-height: 150px
.drag-el
  background-color: #fff
  margin-bottom: 10px
  padding: 5px
// h1
//   color: #fff
//   width: 100%
//   text-align: center
// ul
//   width: 100%
//   background-color: #ccc
//   padding: 15px
//   li
//     width: 95%
//     border: 2px solid #000
//     list-style: none
//     margin-bottom: 5px
//     padding: 10px 5px 10px 20px
//     font-size: 20px
//     color: #fff
//     text-transform: capitalize
//     position: relative
//     display: flex
//     justify-content: space-between
//     &::before
//       content: ''
//       width: 5px
//       height: 5px
//       background-color: #000
//       position: absolute
//       border-radius: 50%
//       bottom: 47%
//       left: 7px
//     button
//       display: block
</style>
