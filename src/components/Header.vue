<template>
    <header>
        <h1>{{ title }}</h1>
    </header>
</template>

<script>
    export default {
        name: 'Header',
        props: {
            title: String
        },
    data() {
        return {
            name: 'Cormac'
        }
    },
    }
</script>

<style scoped>
    header{
        background-color: #111;
        color: #fff;
        padding: 20px;
    }
    h1 {
        margin: 0;
    }
</style>