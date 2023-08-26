<script>

    import {goto}  from '$app/navigation';
    let input= '';
    let active = 'false';

    function submitSearch()
    {
        goto('/search/' + input);
    }
</script>

<form on:submit|preventDefault={submitSearch} class="search">
   {#if !active}
   <label for="search_movie">Search Movie</label>
   {/if}
   <input 
   on:blur={ () => (active = false) } 
   on:focus={ () =>(active = true) }  
   bind:value={input} 
   name="Search_movie"
   type="text"
   class={active ? 'selected' : ''}>

   {#if input}
   <button>Search</button>
   {/if}
</form>

<style>

    .search
    {
        position:relative;
        width:30%;
        margin:1rem;
    }

    button{
        font-size: 0.9rem;
        padding:0rem 1rem;
        background:rgb(96, 110,201);
        color:white;
        font-weight: bold;
        border:none;
        position:absolute;
        bottom:50%;
        right:0;
        transform:translate(0, 50%);
        height:100%;
        border-top-right-radius:10px;
        border-bottom-right-radius: 10px;
        cursor:pointer;

    }

    input
    {
        width:100%;
        border:none;
        font-size:1rem;
        font-family: 'Poppins' , sans-serif;
        outline:none;
        color:rgb(255, 255, 255);
        padding:0.5rem 0.1rem;
        transition:background 0.7s ease-out;
        font-weight: bold;
        background:rgb(63, 63, 63);
        border-radius: 10px;
        padding:1rem;
    }

    label
    {
        position:absolute;
        font-size:0.9rem;
        top:50%;
        left:0;
        transform:translate(0, -50%);
        pointer-events:none;
        color:#fff;
        padding:0rem 1rem;
    }

    input.selected
    {
        background: rgb(50, 50, 50);
    }
</style>