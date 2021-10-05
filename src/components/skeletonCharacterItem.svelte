<div id="main-container">
    <div class="skeleton img"></div>
    <div id="text-container">
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
        <div class="skeleton skeleton-text"></div>
    </div>

</div>

<style>
    #main-container {
        width: 310px;
        border: 1px solid black;
        display: flex;
    }

    #text-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        height: 100%;
    }

    .img {
        width: 130px;
        height: 300px;
        object-fit: cover;
    }

    .skeleton {
        opacity: 0.7;
        animation: skeleton-loading 1s linear infinite alternate;
    }

    .skeleton-text {
        width: 80%;
        height: 0.5rem;
        margin-bottom: .25rem;
        border-radius: .125rem;
        margin-bottom: 0.25rem;
        margin-top: 20px;
    }

    @keyframes skeleton-loading {
        0% {
            background-color: hsl(200,20%,70%);
        }
        
        100% {
            background-color: hsl(200,20%,85%);
        }
    }
</style>