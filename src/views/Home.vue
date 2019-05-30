<template>
    <div id="app">
        <Header />
        <AddTodo v-on:add-todo="addTodo" />
        <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    </div>
</template>

<script>
    import Todos from '../components/Todos.vue';
    import AddTodo from '../components/AddTodo';
    import Axios from 'axios';
    export default {
        name: 'Home',
        components: {
            Todos,
            AddTodo
        },
        data(){
            return{
                todos:[]
            }
        },
        methods: {
            deleteTodo(id){
                //this.todos=this.todos.filter(todo=>todo.id !==id);
                Axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
                    .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
                    .catch(error => console.log(error));

            },
            addTodo(newTodo) {
                const { title, completed }= newTodo;

                Axios.post('https://jsonplaceholder.typicode.com/todos',{
                    title,
                    completed
                })
                    .then(res => this.todos = [...this.todos, res.data] )
                    .catch(error => console.log(error));

                //this.todos=[...this.todos, newTodo]; // we use it without API
            },
        },

        created() {
            Axios.get('https://jsonplaceholder.typicode.com/todos?_limit=10')
                .then(res => this.todos = res.data)
                .catch(err => console.log(err))
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
    * {
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;
        margin: 0;
        padding: 0;

    }

    body{
        font-family: Arial,Helvetica,sans-serif;
        line-height: 1.4;
    }

    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #ffff;
        padding: 7px 20px;
        cursor: pointer;
    }
    .btn:hover{
        background: #103db8;
    }
</style>
