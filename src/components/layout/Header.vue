<template>
    <header class="header">
        <div id="nav">
            <router-link to="/">Home</router-link>  |
            <router-link to="/about">About</router-link>
        </div>
    </header>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped>
    .header {
        background: dodgerblue;
        color: #fff;
        text-align: left;
        padding: 10px;
    }
    .header a {
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
    }

</style>