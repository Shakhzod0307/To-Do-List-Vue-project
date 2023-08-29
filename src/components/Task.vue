<template>
    <div class="task">
        <h4>
            {{ task.text }}
            <button type="button" @click="onDelete(task.id)" class="btn btn-danger">X</button>
        </h4>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>


export default{
    name: 'Task',
    props:{
        task: Object
    },
    methods:{
        onDelete(id){
           this.$emit('delete-task', id)
        }
    },
    emits: ['delete-task']
}
</script>

<style scoped>

.task{
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
.task.reminder{
    border-left: 5px solid green;
}

.task h4{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.task p{
    align-items: start;
    width: 700px;
    padding-right:580px;
}
</style>