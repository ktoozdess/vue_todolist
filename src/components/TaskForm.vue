<template>
<div>
    <form @submit.prevent>
      <input type="text" v-model="todo.title" class="form-control" placeholder="title" name="title">
      <input type="text" v-model="todo.descr" class="form-control" placeholder="description" name="descr">
      <button @click="addTodo">Add Task</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default{
    data(){
        return{
            todo:{
            title: '',
            descr: ''
            }
            
        }
    },
    methods: {
        addTodo(){
            this.todo.id = uuidv4();
            this.$emit('add-todo', this.todo);
            this.todo = {
            title: '',
            descr: ''
            }
           
        }
    }

}

</script>

<style>


</style>