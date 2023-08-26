<script>
export /**
* @type {any}
*/
     let movies;
</script>


<div class="movieCard">
    <a href={'/movies/' + movies.id}>
    <img src="{ 'https://image.tmdb.org/t/p/w500' + movies.poster_path}" alt="{movies.title}" />
    </a>

    
    <div class="description">
        <h2>{movies.title}</h2>
        <p>
            {movies.release_date}
        </p>
    </div>
</div>


<style>
    img
    {
        width:100%;
        height:50vh;
        object-fit: cover;
        border-radius: 1rem;
        margin-bottom: 1rem;
    }

    h2{
        font-size: 0.9rem;

    }

    .description
    {
        height:7vh;
    }

    p
    {
        font-size:0.9rem;
    }

    .movieCard
    {
      display:flex;
      flex-direction: column;
      justify-content: space-around;
      padding:1rem;
    }

</style>