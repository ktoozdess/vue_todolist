<template>
<div>
    {{ TaskItem.title }} 
    <br>
    {{ TaskItem.descr }}

</div>
</template>

<script>
export default{
    name: 'TaskItem',
    props: [
      'TaskItem'  
    ]
}

</script>

<style lang="scss" scoped>


</style>