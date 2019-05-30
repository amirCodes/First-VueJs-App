<template>
    <div class="about">
        <h1>About</h1>
        <p>This is the TodoList which includes the following functionality</p>
        <ui>
            <li>fetch the to do list using API</li>
            <li>Add to do task using API</li>
            <li>Delete task using API</li>
            <li>Check box which mark as done the task</li>
        </ui>
    </div>
</template>

<script>
    export default {
        name: "About"
    }
</script>

<style scoped>
 ui{
     float: contour;
     text-align: left;
     margin-left: 10px;
 }
</style>