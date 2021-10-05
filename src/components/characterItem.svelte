<script>
    export let character
    console.log('CH: ', character)
</script>

<div id="main-container">
    <img class="img" src="{character.thumbnail.path}.{character.thumbnail.extension}" alt="character">
    <div id="text-container">
        <p>{character.name}</p>
        <p>{character.name}</p>
    </div>
</div>

<style>
    #main-container {
        width: 310px;
        border: 1px solid black;
        display: flex;
    }

    .img {
        width: 130px;
        height: 300px;
        object-fit: cover;
    }
</style>