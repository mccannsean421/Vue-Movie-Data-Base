<template>
    <div>
        Movies list
        <ul>
            <li>{{ movie.original_title }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "MoviesList",
        data: function() {
            return {
                movie: {}
            }
        },
        created: function() {
            this.fetchData()
        },
        methods: {
            fetchData: async function() {
                try {
                    const res = await fetch('https://api.themoviedb.org/3/movie/550?api_key=39c3e7befb37432f892ebd79b38ddfe6');
                    const movie = await res.json();
                    this.movie = movie;
                } catch(error) {
                    console.error(error);
                }
            }
        }
    }
</script>

<style>

</style>