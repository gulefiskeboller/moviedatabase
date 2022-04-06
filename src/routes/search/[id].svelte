<script context="module">
    export async function load({fetch, params}) {
        const res = await fetch(
            `https://api.themoviedb.org/3/search/movie?api_key=b08fe16aed14e160ab049b616ea75955&language=en-US&query=${params.id}&page=1&include_adult=false`
            );
        const data = await res.json();
        if (res.ok){
            return {
                props: { searchedMovie: data.results }
            }
        }
    }
</script>
<script>
    import MovieCard from "../../components/MovieCard.svelte";
    export let searchedMovie;
</script>

<div class="searched-movies">
    {#each searchedMovie as movie}
    <MovieCard {movie}g/>
    {/each}
</div>
<style>
    .searched-movies {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        grid-column-gap: 1rem;
        grid-row-gap: 2rem;
        height: 20vh;
    }
</style>