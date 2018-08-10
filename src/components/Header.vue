<template>
    <header>
        <h1>{{ title }}</h1>
        <h2>{{ newTitle }}</h2>
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
        computed: {
            newTitle: function() {
                console.log(this.title);
                console.log(this.name);
                return this.name.toLowerCase();
            }
        }
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