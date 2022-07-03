<template>
<div>
    <ul>
    <li v-for="item in todoEntries" v-bind:key="item.id">
         <task-item v-bind:TaskItem="item" @deleteTask="$emit('deleteTask', item.id)" />
         <br>
    </li>
    </ul>
    
</div>
</template>

<script>
import TaskItem from '@/components/TaskItem'

export default{
    name: 'TaskList',
    components: {
        TaskItem
    },
    props: [
        'todoEntries'
    ]
}

</script>

<style lang="scss" scoped>
    ul{
        margin: 0px;
        padding: 20px 40px;
    }
    li{
        
    }

</style>