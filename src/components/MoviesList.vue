<template>
    <div>
        <ul>
            <li v-for="movie in movies"><Movie :movie="movie" /></li>
        </ul>
    </div>  
</template>

<script>
    import Movie from './Movie.vue';

    export default {
        name: "MoviesList",
        data: function() {
            return {
                movies: []
            }
        },
        components: {
            Movie
        },
        created: function() {
            this.fetchData()
        },
        methods: {
            fetchData: async function() {
                try {
                    const res = await fetch('https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=39c3e7befb37432f892ebd79b38ddfe6');
                    const movies = await res.json();
                    
                    this.movies = movies.results;
                } catch(error) {
                    console.error(error);
                }
            }
        }
    }
</script>

<style scoped>
    ul {
        list-style: none;
        display: grid;
        padding: 1rem;
        margin: 0;
        grid-gap: 1rem;
        grid-template-columns: repeat(6, 1fr);
    }
</style>