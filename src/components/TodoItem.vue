<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <input type="checkbox" v-on:change="markComplete">
        <p>{{todo.title}}</p>
        <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props:["todo"],
        methods: {
            markComplete(){
                this.todo.completed= !this.todo.completed;
            }
        }
    }
</script>

<style scoped>
 .todo-item{
     background: aliceblue;
     padding: 10px;
     display: flex;
     border-bottom: 1px #ccc dotted;
 }
    .is-complete {
        text-decoration: line-through;
        background-color: lightgreen;
    }
    .del{
        background: #ff0000;
        color: #fff;
        margin-right: 400px;
        margin-left: auto;
        vertical-align: top;
        margin-bottom: 15px;
        padding: 2px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
    p {
        padding-left: 100px;
    }
    input[type='checkbox'] {
        padding-left: 50px;
    }
</style>