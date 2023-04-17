<script lang="ts">
  import { each } from "svelte/internal";
  import albums from "../utils/TestAlbums";
  export let id;
  let album = albums.find((element) => element.id === id);
  console.log(album);
</script>

<div class="album-header">
  <img class="album-cover-image" alt="album-{album.index}" src={album.cover} />
  <div class="album-header-text">
    <h1>{album.title}</h1>
    <span class="author-name">{album.author}</span>
  </div>
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
    display: flex;
    background-color: var(--background-color-light);
    align-items: center;
    padding: 1vw;
    justify-content: left;
    padding-left: 15vw;
  }
  .album-header-text{
    text-align: left;
    padding: 3vw;
  }
  .author-name{
    font-size: 16pt;
  }
  .song-list-container {
    margin-left: 18vw;
    margin-right: 18vw;
    text-align: left;
    font-size: 14pt;
  }
  .song-list {
    text-align: left;
    padding: 0;
  }
  .song {
    background-color: var(--background-color-light);
    text-align: left;
    padding: 0.5vh 1vw;
    list-style-position: inside;
    border: 1px solid var(--accent-color);
    border-bottom: none;
  }
  .song:last-of-type{
    border: 1px solid var(--accent-color);
  }
  .song:hover {
    background-color: var(--background-color-highlight);
    cursor: pointer;
  }
  .album-cover-image {
    margin: 0.5vw;
    width: clamp(150px, 15vw, 15vw);
    border: 1px solid var(--accent-color);
  }
</style>
