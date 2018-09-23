<template>
    <div class="movie-wrapper" :style="styles">
        <div class="movie-info">
            <h1>{{ movie.title }}</h1>
            <time>{{ movie.release_date }}</time>
            <p>{{ movie.overview }}</p>
        </div>
    </div>
</template>

<script>
    const BACKDROP_PATH = "http://image.tmdb.org/t/p/w1280";
    export default {
        name: "MovieDetail",
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
                    const res = await fetch(`https://api.themoviedb.org/3/movie/${this.$route.params.id}?api_key=39c3e7befb37432f892ebd79b38ddfe6`);
                    const movie = await res.json();
                    console.log(movie)
                    this.movie = movie;
                } catch(error) {
                    console.error(error);
                }
            }
        },
        computed: {
            styles() {
                console.log(`url('${BACKDROP_PATH}/${this.movie.backdrop_path}') no-repeat`);
                return {
                    background: `url(${BACKDROP_PATH}/${this.movie.backdrop_path}) no-repeat`
                }
            }
        }
    }
</script>

<style scoped>
    .movie-wrapper {
        color: #fff;
        padding-top: 50vh;
        position: relative;
        background-size:cover;
        background-position: center;
    }

    .movie-info {
        color: #222;
        background: #fff;
        padding: 2em 1em;
    }
</style>