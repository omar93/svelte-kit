<script>
    export let character
    console.log('character: ', character)
</script>

<div id="main-container">
    <img src="{character.thumbnail.path}.{character.thumbnail.extension}" alt="">
    <p>{character.name}</p>
</div>

<style>
    #main-container {
        border: 1px solid black;
        display: flex;
        flex-direction: column;
    }
    img {
        width: 200px;
    }
</style>