<script lang="ts">

</script>
<main>
    <h1>Recommended</h1>
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
    .album-list{
        display: flex;
    }
    .album-cover{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .album-cover-image{
        margin: 0.5vw;
        width: 15vw;
        transition: 0.2s;
        box-shadow: 0px 0px 5px 5px rgb(50,0,100);
    }
    .album-cover-image:hover{
        margin: 0;
        width: 16vw;
        box-shadow: 0px 0px 5px 5px rgb(128, 0, 255);
    }
    .album-title{
        font-weight: 400;
        font-size: 15pt;
        padding: 15px;
    }
</style>
