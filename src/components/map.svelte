<script>
    export let characters
    console.log(characters)
    // svrige är 2 timmar+ jämför med api, så om mappen startar kl 23 enligt api är kl 01 i sverige
    let timeEmaining = `${characters.battle_royale.current.start-characters.battle_royale.current.end}` 
</script>

<div class="main-container">
    <ul>
        <li>
            Current map: {characters.battle_royale.current.map}
            <img src="{characters.battle_royale.current.asset}" alt="">
        </li>
        <li>
            Time left on rotation: {timeEmaining}
        </li>
    </ul>
</div>

<style>
    ul {
        padding: 0;
        margin: 0;
        list-style: none;
    }
    img {
        width: 1000px;
    }
</style>