 
<template>

<form @submit="onSubmit" class="add-form mb-5">
    <div class="row col-12 form-group">
        <label class="col-3" for="text">Add Task</label>
        <input type="text" v-model="text" id="text" name="text" class="col-9 form-control" placeholder="">
    </div>
    <div class="row col-12 form-group">
        <label class="col-3" for="day">Add Date</label>
        <input type="text" v-model="day" id="day" name="day" class="col-9 form-control" placeholder="">
    </div>
    <div class="row col-12 ml-3 form-group form-group-check">
        <input  type="checkbox" v-model="reminder" value="reminder"> 
        <label class="ml-2">Checked</label>
    </div>
    <input type="submit" id="submit_save" class="col-11 ml-4 btn btn-block" value="Save task">
</form>

</template>

<script>
export default{
    name: 'AddTask',
 
    data() {    
        return {    
            text: '',
            day: '',
            reminder: false
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault();
            if(!this.text){
                alert("Please enter the text")
                return
            }
            const newTask = {
                id: Math.floor(Math.random() *100000),
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }
      
            this.$emit('add-task',newTask),
            this.text = '',
            this.day = '',
            this.reminder = false

        }
    }
}
</script>

<style scoped>

#submit_save{
    background-color: black;
    color: white;
}

</style>