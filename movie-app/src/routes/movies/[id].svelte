<script context="module">
    
    // @ts-ignore
    export async function load( {fetch, params} )
    {
      console.log("params id" , params.id);
      console.log("hello");
      const res = await fetch(`https://api.themoviedb.org/3/movie/${params.id}}?api_key=00f18f62f1339acd38f45ceabf0531b5&language=en-US`);
      const movieDetail = await res.json();
      //console.log(data);
      if (res.ok)
      {
          return {
             props :{ movieDetail }
          };
      }
    }
</script>

<script>
     export /**
* @type {{ backdrop_path: string; }}
*/
      let movieDetail;
     console.log("Movie details " , movieDetail );
</script>


<div class="movie-details">
    <div class="movie-image">
        <img src={'https://image.tmdb.org/t/p/w500' + movieDetail.backdrop_path} alt={movieDetail.title}>
                  
    </div>
    <div class="movie-text">
        <h1>{movieDetail.title}</h1>
        <p>
            overview: {movieDetail.overview}
        </p>
        <p>
            <span>Release date:</span>
            {movieDetail.release_date}<br/>

            <span>Budget:</span>
            { movieDetail.budget}<br/>

            <span>Rating:</span>
            {movieDetail.vote_average}<br/>

            <span>Runtime:</span>
            {movieDetail.runtime}<br/>
        </p>
    </div>
</div>

<style>
    h1
    {
        padding: 1rem rem 2rem;
    }
    
    p{
       padding: 1rem 0rem;
    }

    .movie-image
    {
     width:100%;
    }

    img{
     width:100%;
     border-radius:1rem;
    }

    span{
     font-weight: bold;
    }

    .movie-details
    {
     margin:2rem 20%;
    }
</style>