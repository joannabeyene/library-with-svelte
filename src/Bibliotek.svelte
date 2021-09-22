<script>
	import Movies  from "./Movies.svelte";
    import { onMount } from "svelte";
	export let movie = [];
    onMount(()=> {
        setTimeout(() => {
            fetch('http://localhost:3000/movies')
        .then(res=> res.json())
        .then(data => {
            console.log(data);
            movie = data;
        })
        }, 2000);
    })
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<main>
	<h1>Library Movie Selection!</h1>
    {#each movie as movies}
    <Movies {movies}/>
    {:else}
    <div><strong><i>Getting movies...</i></strong></div>
    {/each}
</main>