

<template>
<button @click="onClick()" :style="{ background: color }" class="btn btn-dark">{{ text }}</button>
</template>

<script>
export default{
    name: "Button",
    props:{
        text: String,
        color: String,
    },
    methods:{
        onClick(){
            this.$emit('toggle-add-task')
        }
    }
}
</script>

<style scoped>
.btn{
    margin-left: 200px;
}
</style>