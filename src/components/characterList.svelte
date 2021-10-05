<script>
    import Character from './characterItem.svelte'
    export let characters = []
</script>
<p>characerList</p>
<ul>
    {#each characters as character}
    <li>
        <Character {character}/>
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