<script>
    import Banner from '../components/banner.svelte'
    import Nav from '../components/nav.svelte'
</script>

<div id="layout-container">
    <Banner/>
    <Nav/>
    <div id="slot-container">
        <slot></slot>
    </div>
</div>


<style>
    #layout-container {
        display: flex;
        flex-direction: column;
        width: 1000px;
        margin: auto;
        padding: 10px;
        position: sticky;
    }

    #slot-container {
        margin-top: 50px;
    }
</style>
