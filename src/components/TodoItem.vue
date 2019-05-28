<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <input type="checkbox" v-on:change="markComplete">
        <p>{{todo.title}}</p>
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
     border-bottom: 1px #ccc dotted;
 }
    .is-complete {
        text-decoration: line-through;
        background-color: lightgreen;
    }
    .del{
        background: #ff0000;
        color: #fff;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>