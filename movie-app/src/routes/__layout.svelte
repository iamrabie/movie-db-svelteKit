<script>
  import '../styles/global.css';
  import Nav from '../components/nav.svelte';
</script>
<svelte:head>
    <title>
       The Movie DB
    </title>
</svelte:head>

<Nav />

<main>
    <slot></slot>
</main>
