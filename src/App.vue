<template>
  <div class="main">
  <header-todo class="header-todo" />
  <TaskForm @add-todo="addTodo" />
  <task-list v-bind:todoEntries="todoEntries"  @deleteTask="deleteTaskItem" class="task-list" />

  </div>
</template>

<script>
import HeaderTodo from '@/components/Header'
import TaskList from '@/components/TaskList'
import TaskForm from '@/components/TaskForm'


  export default{
    components: {
    HeaderTodo,
    TaskList,
    TaskForm
},
    data(){
      return{
        todoEntries: [
          {
            id: 1,
            title: 'Buy Milk',
            descr: 'Look at the Date',
            completed: false
          },
          {
            id: 2,
            title: 'Buy Bananas',
            descr: 'Yellow',
            completed: false
          },
          {
            id: 3,
            title: 'Buy Headphones',
            descr: 'Black',
            completed: false
          },
        ]
      }
    },
    methods: {
      addTodo(todo){
      this.todoEntries.push(todo);
      },
      deleteTaskItem(todoId){
        this.todoEntries = this.todoEntries.filter(item => item.id !== todoId)
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
