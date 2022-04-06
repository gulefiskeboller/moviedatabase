<script>
    export let popular;
    console.log(popular[0])
    import MovieCard from './MovieCard.svelte'
</script>

<h3>Popular movies:</h3>

<div class="popular-movies">
    {#each popular as movie}
    <MovieCard {movie} />
    {/each}

<style>
h3{
    padding: 0 1rem;
}
.popular-movies{
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-column-gap: 1rem;
    grid-row-gap: 2rem;
}
h3{
        font-size: x-large;
        font-family: 'Courier New', Courier, monospace;
        
    }
    h2{
        font-size: 0.9rem;

    }
    .descrpition{
        height: 5vh;

    }
    p{
        font-size: 0.7rem;
    }
    .movie-card{
        display: flex;
        flex-direction: column;
        justify-content:space-around;
        padding: 1rem;
        
    }
</style>
</div>