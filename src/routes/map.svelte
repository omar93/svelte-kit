<script>
    import SkeletonCharacterItem from '../components/skeletonCharacterItem.svelte'
    import Map from '../components/map.svelte'

    let mapUrl = 'https://api.mozambiquehe.re/maprotation?version=2&auth='

    function getData() {
    const fullUrl = mapUrl+'6dNEF06dFgBxPXsKVEtv'
    return fetch(fullUrl).then(resp => {
        return resp.json().then(data => {
                return data
            })
        })
    }

    let korv = getData()
    korv.then(resp => {
        console.log(resp)
    })
    


</script>

<div>
    {#await getData()}
    <ul>
        {#each Array(6) as _, i}
            <li>
                <SkeletonCharacterItem/> 
            </li>
        {/each}
    </ul>
    {:then characters} 
        <Map {characters}/>
    {/await}
</div>

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