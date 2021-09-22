<script>
export let movies = [];
</script>

<style>
	div {
        margin: 10px;
        margin-left: 24%;
        padding: 10px;
        border: 2px solid red;
        max-width: 50%;
    }
</style>

<main>
    <div><strong>Movie: </strong> <i>{movies.movieTitle}</i><br/>
        <strong>Director: </strong>{movies.director}</div>
</main>