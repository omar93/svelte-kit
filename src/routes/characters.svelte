<script>
    import CharacterList from '../components/characterList.svelte'
    import md5 from 'blueimp-md5'
    
    function getData() {
        const timeStamp = Date.now()
        const privateKey = 'ba965667979b9e2c1ec8279f3aef41783dab7df2'
        const publicKey = '0585a00c1f7c82b3522ec650666e31f6'
        const hash = md5(timeStamp+privateKey+publicKey)
        const characterUrl = `https://gateway.marvel.com/v1/public/characters?ts=${timeStamp}&apikey=${publicKey}&hash=${hash}`
        return fetch(characterUrl).then(resp => {
            return resp.json().then(data => {
                return data.data.results
            })
        })
    }



</script>

<div>
    {#await getData()}
        <p>Loading character data</p>
    {:then characters} 
        <CharacterList {characters}/>
    {/await}
        
</div>