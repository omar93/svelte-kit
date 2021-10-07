<script>
    export let character
    console.log('CH: ', character)
</script>

<div id="main-container">
    <img class="img" src="{character.thumbnail.path}.{character.thumbnail.extension}" alt="character">
    <div id="text-container">
        <p>Name: {character.name}</p>
    </div>
</div>

<style>
    #main-container {
        width: 170px;
        height: 170px;
        border: 1px solid black;
        display: flex;
    }

    .img {
        width: 50%;
        object-fit: cover;
    }
</style>