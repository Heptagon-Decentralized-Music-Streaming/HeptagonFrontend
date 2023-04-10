<script lang="ts">
  import { link } from "svelte-navigator";
  import { text } from "svelte/internal";
  import albums from '../utils/TestAlbums';
</script>
  <h1 class="page-title">Decentralized Music Streaming</h1>
  <input class="search-bar" placeholder="Find new music..." />
  <h2 class="page-title">Recommended</h2>
  <div class="album-list">
    {#each albums as album, index}
      <a class="album-cover" use:link href="/album/{album.id}">
        <img
          class="album-cover-image"
          alt="album-{index}"
          src={album.cover}
        />
        <span class="album-title">{album.title}</span>
      </a>
    {/each}
  </div>

<style>
  .page-title {
    font-size: 25pt;
    font-weight: 500;
    padding: 2vh;
  }
  .album-list {
    padding: 1vw;
    flex-wrap: wrap;
    display: flex;
    justify-content: center;
  }
  .album-cover {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .album-cover-image {
    margin: 0.5vw;
    width: clamp(150px, 15vw, 15vw);
    transition: 0.2s;
    border: 2px solid rgb(100, 0, 200);
  }
  .album-cover-image:hover {
    margin: 0;
    width: 16vw;
    box-shadow: 0px 0px 5px 5px rgb(128, 0, 255);
  }
  .album-title {
    width: clamp(150px, 15vw, 15vw);
    font-weight: 400;
    font-size: 15pt;
    padding: 15px;
  }
  .search-bar {
    margin-bottom: 1vh;
    padding-left: 15px;
    padding-right: 15px;
    width: 70%;
    height: 4vh;
    border-radius: 20px;
    font-family: Avenir;
    font-size: 15pt;
    border: none;
  }
</style>
