<template>
<div v-bind:class="{ 'completed' : TaskLocal.completed }" >
    <p @click="markComplete" class="title"> {{ TaskItem.title }} </p>
   <p @click="markComplete" class="descr">{{ TaskItem.descr }}</p>
    <button @click="$emit('deleteTask', TaskItem.id)" >Delete</button>
</div>
</template>

<script>
export default{
    name: 'TaskItem',
    props: [
      'TaskItem'  
    ],
    data(){
        return{
            TaskLocal: this.TaskItem
        }
    },
    methods: {
        markComplete(){
            this.TaskLocal.completed = !this.TaskLocal.completed
        },
    
    }
}

</script>

<style lang="scss" scoped>
    p{
        margin: 10px 0px;
    }
    .title{
        font-size: 26px;
    }
    .descr{
        opacity: 0.8;
        font-size: 18px;
        }
        .completed {
        text-decoration: line-through;
      }

</style>