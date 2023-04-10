<script lang="ts">

</script>
<main>
    <span class="page-title">Recommended</span>
    <div class="album-list">
        <div class="album-cover">
            <img class="album-cover-image" alt="album-1" src="https://source.boomplaymusic.com/group10/M00/11/18/e84753221e1f48859b67e0b4ba3bc927_320_320.jpg"/>
            <span class="album-title">The Godfather Soundtrack</span>
        </div>
        <div class="album-cover">
            <img class="album-cover-image" alt="album-1" src="https://source.boomplaymusic.com/group10/M00/11/18/e84753221e1f48859b67e0b4ba3bc927_320_320.jpg"/>
            <span class="album-title">The Godfather Soundtrack</span>
        </div>
    </div>
</main>
<style>
    .page-title{
        font-size: 25pt;
        font-weight: 500;
        padding: 2vh;
    }
    .album-list{
        padding: 1vw;
        flex-wrap: wrap;
        display: flex;
        justify-content: center;
    }
    .album-cover{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .album-cover-image{
        margin: 0.5vw;
        width: clamp(150px,15vw,15vw);
        transition: 0.2s;
        box-shadow: 0px 0px 5px 5px rgb(50,0,100);
    }
    .album-cover-image:hover{
        margin: 0;
        width: 16vw;
        box-shadow: 0px 0px 5px 5px rgb(128, 0, 255);
    }
    .album-title{
        width: clamp(150px,15vw,15vw);
        font-weight: 400;
        font-size: 15pt;
        padding: 15px;
    }
</style>
