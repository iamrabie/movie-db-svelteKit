<script context="module">
import { dataset_dev } from "svelte/internal";


    // @ts-ignore
    export async function load( {fetch, params} )
    {
      
      console.log("params" ,params);
      const res = await fetch(`https://api.themoviedb.org/3/search/movie?api_key=00f18f62f1339acd38f45ceabf0531b5&language=en-US&query=${params.id}&page=1&include_adult=false`);
      
      const data= await res.json();
      //console.log(data);
      if (res.ok)
      {
          return {
             props :{ searchedMovie: data.result}
          };
      }
    }
</script>

<script>

    export /**
* @type {any}
*/
     let searchedMovie;
     console.log("searched movies" , searchedMovie);
     import MovieCard from "../../components/movieCards.svelte";

</script>


<div class="searched-movie">
    {#each searchedMovie as movies}
       <MovieCard {movies}/>
    {/each}
</div>

<style>
    
    .searched-movie
    {
        display:grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        grid-column-gap:1rem;
        grid-row-gap:2rem;
        height:20vh;
    }

</style>