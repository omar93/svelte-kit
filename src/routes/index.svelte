<script>
    import md5 from '../lib/md5.js'

    const timeStamp = Date.now()
    const privateKey = 'ba965667979b9e2c1ec8279f3aef41783dab7df2'
    const publicKey = '0585a00c1f7c82b3522ec650666e31f6'
    const hash = md5(timeStamp+privateKey+publicKey)
    const url = `https://gateway.marvel.com/v1/public/characters?ts=${timeStamp}&apikey=${publicKey}&hash=${hash}`
    const getData = async () => {
        let result = await fetch(url)
        let data = await result.json()
        let name = data.data.results
        console.log(name)
    }
    getData()
</script>

<div id="main-container">
    <span>
        Home
    </span>
</div>

<style>
    #main-container {
        display: flex;
        justify-content: center;
    }
</style>