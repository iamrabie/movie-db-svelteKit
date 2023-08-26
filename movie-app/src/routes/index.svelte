<script context="module">
    // @ts-ignore
    export async function load( {fetch} )
    {
      const res = await fetch('https://api.themoviedb.org/3/movie/popular?api_key=00f18f62f1339acd38f45ceabf0531b5&language=en-US&page=1');
      const data = await res.json();
      //console.log(data);
      if (res.ok)
      {
          return {
              props: { popular: data.results }
          };
      }
    }
</script>

<script>

    import PopularMovies from '../components/popMovies.svelte';
    export /**
* @type {any}
*/
     let popular;
    //console.log(popular);
</script>

<header>
    <PopularMovies {popular}/>
</header>