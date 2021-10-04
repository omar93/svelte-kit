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
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
        list-style-type:none;
        margin: 0px;
        padding:0px;
    }

    li {
        margin-top: 30px;
        margin-left: 10px;
    }
</style>