<script>
    import CharacterList from '../components/characterList.svelte'
    import SkeletonCharacterItem from '../components/skeletonCharacterItem.svelte'
    import { dummyData } from '../lib/dummyData.js'
    import md5 from 'blueimp-md5'
    function getData() {
        const timeStamp = Date.now()
        const privateKey = 'ba965667979b9e2c1ec8279f3aef41783dab7df2'
        const publicKey = '0585a00c1f7c82b3522ec650666e31f6'
        const hash = md5(timeStamp+privateKey+publicKey)
        const characterUrl = `https://gateway.marvel.com/v1/public/characters?offset=600&ts=${timeStamp}&apikey=${publicKey}&hash=${hash}`
        return fetch(characterUrl).then(resp => {
            return resp.json().then(data => {
                return data.data.results
            })
        })
    }



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
        <CharacterList {characters}/>
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