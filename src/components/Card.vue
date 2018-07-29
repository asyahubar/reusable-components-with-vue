<template>
    <div class="card">
        <img :src="msg.image" alt="illustration">
        <p class="price">{{ msg.price }}$</p>
        <p class="title">{{ msg.title }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Card',
        props: {
            msg: { required: true }
        }
    }
</script>

<style>
    h3 {
        margin: 40px 0 0;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        display: inline-block;
        margin: 0 10px;
    }
    a {
        color: #42b983;
    }
    .card {
        padding: 6px;
        margin: 3px;
        min-width: 300px;
        height: 300px;
        display: inline-block;
        background-color: lightpink;
        border-radius: 5px;
    }
    .card img {
        max-width: 294px;
        height: 200px;
    }
    .card .title {
        padding: 4px 0;
        color: deeppink;
        font-weight: bold;
        background-color: rgba(40, 40, 40, 0.1);
    }
</style>
