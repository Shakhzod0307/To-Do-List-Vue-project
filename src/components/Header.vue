

<template>

<header>
    <h1>{{ title }}</h1>
    <Button 
    @toggle-add-task="$emit('toggle-add-task')" 
    :text="ShowAddTask ? 'Hide ': 'Add Task' " 
    :color="ShowAddTask ? 'crimson ': 'green'" 
    />


</header>

</template>




<script>
import Button from '@/components/Button.vue';

export default{
    name: "Header",
    
    props:{
        title: String,
        ShowAddTask: Boolean,

    },
    components:{
        Button
    }
}
</script>

<style>
 header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}


</style>