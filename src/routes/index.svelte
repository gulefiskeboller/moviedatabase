<script context="module">

    export async function load({fetch}){

        const res = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=b08fe16aed14e160ab049b616ea75955&language=en-US&page=1');

        const data = await res.json();

        if (res.ok){

            return{

                props: {popular: data.results}

            }

        }

    }

</script>



<script>

    import PopularMovies from '../components/PopularMovies.svelte'
    import SearchMovies from '../components/SearchComponents.svelte'
    import {fly} from "svelte/transition"
    export let popular;
    import global from "../global.css"

</script>



<section in:fly={{y:50, duration:500, delay:500}} out:fly={{duration:500}}>
    <SearchMovies />
    <PopularMovies {popular}/>
</section>