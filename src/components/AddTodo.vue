<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="add to do...">
            <input type="submit" value="Submit" class="btn">

        </form>
        <h4>To do list</h4>
        <hr>
    </div>
</template>

<script>
    import uuid from 'uuid';
    export default {
        name: "AddTodo",
        data(){
            return{
                title:''
            }
        },
        methods: {
            addTodo(e){
                e.preventDefault();
                const newTodo ={
                    id:uuid.v4(),
                    title: this.title,
                    completed:false,
                }
                // Send up tp parent
                this.$emit('add-todo', newTodo);

                this.title='';
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
    }
    input[type="text"] {
        align-content: center;
        margin-left: 10%;
        margin-bottom: 10px;
        width: 80%;
        border: 1px solid #00ff1e;
        }
    input[type="submit"] {
        align-content: center;
        margin-left: 1%;
        margin-bottom: 10px;
        margin-top: 5px;
        padding: 10px;
        border: 1px solid #c5d5fa;
    }
    h4 {
        text-align: left;
    }
</style>