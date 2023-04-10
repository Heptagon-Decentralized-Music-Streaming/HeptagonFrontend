<script lang="ts">
  import { each } from "svelte/internal";
  import albums from "../utils/TestAlbums";
  export let id;
  let album = albums.find((element) => element.id === id);
  console.log(album);
</script>

<div class="album-header">
  <img class="album-cover-image" alt="album-{album.index}" src={album.cover} />
  <h1>{album.title}</h1>
</div>
<div class="song-list-container">
  <ol class="song-list">
    {#each album.songs as song}
        <li class="song">{song}</li>
    {/each}
  </ol>
</div>

<style>
  .album-header {
    width: 100%;
    display: flex;
    align-items: center;
    background-color: rgb(40, 0, 80);
    padding: 1vw;
    justify-content: left;
    padding-left: 15vw;
  }
  .song-list-container {
    margin-left: 18vw;
    text-align: left;
    width: 50%;
    font-size: 14pt;
  }
  .song-list{
    text-align: left;
    padding: 0;
  }
  .song{
    background-color: rgb(40, 0, 80);
    text-align: left;
    padding: 0.5vh 1vw;
    list-style-position:inside;
    border: 1px solid rgb(100, 0, 200);
  }
  .song:hover{
    background-color: rgb(50, 0, 100);
    cursor: pointer;
  }
  .album-cover-image {
    margin: 0.5vw;
    width: clamp(150px, 15vw, 15vw);
  }
</style>
