<template>
  <div class="main">
  <header-todo class="header-todo" />
  <task-list v-bind:todoEntries="todoEntries" class="task-list" />
  </div>
</template>

<script>
import HeaderTodo from '@/components/Header'
import TaskList from '@/components/TaskList'

  export default{
    components: {
      HeaderTodo, TaskList
    },
    data(){
      return{
        todoEntries: [
          {
            id: 1,
            title: 'Buy Milk',
            descr: 'Look at the Date'
          },
          {
            id: 2,
            title: 'Buy Bananas',
            descr: 'Yellow'
          },
          {
            id: 3,
            title: 'Buy Headphones',
            descr: 'Black'
          },
        ]
      }
    },

  }
</script>

<style lang="scss" scoped>
  .main{
    max-width: 700px;
    margin: 0 auto;
  }
  .header-todo{
    background-color: rgb(203, 255, 151);
  }
  .task-list{
    background-color: rgb(140, 140, 140);
  }

</style>
