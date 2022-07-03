<template>
<div>
    <form @submit.prevent>
      <input type="text" v-model="todo.title" class="form-control" placeholder="title" name="title">
      <input type="text" v-model="todo.descr" class="form-control" placeholder="description" name="descr">
      <button class="btn btn-success" @click="addTodo">Add Task</button>
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
            },
            
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

<style lang="scss" scoped>
    form{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background-color: rgb(140, 140, 140);
        border-bottom: 1px solid #198754;
        input{
            max-width: 500px;
            margin: 10px;
        }
        .btn{
           margin: 10px; 
        }
    }

</style>