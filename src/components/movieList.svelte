<script>
    import MovieItem from './movieItem.svelte'
    let movies = ['avengers','batman','ironman','gemberss',
    'avengers','batman','ironman','gemberss','avengers','batman','ironman','gemberss','fisk','apa','korv','what']
</script>

<ul>
    {#each movies as movie}
    <li>
        <MovieItem/>
    </li>
    {/each}
</ul>

<style>
    ul {

        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        gap: 20px;
    }
</style>