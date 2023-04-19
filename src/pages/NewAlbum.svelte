<script>
  import NewAlbumButton from "../components/NewAlbumButton.svelte";
  import FaPlus from 'svelte-icons/fa/FaPlus.svelte'
  let album = {
    songs: []
  }
</script>

<div class="header">
  <h2 class="title">Create a New Album</h2>
  <NewAlbumButton />
</div>
<div class="song-list-container">
    <ol class="song-list">
      {#each album.songs as song}
        <li class="song">{song}</li>
      {/each}
      <li class="song nostyle">
        <div class="icon">
            <FaPlus/>
        </div>
        Add track</li>
    </ol>
  </div>

<style>
    .icon{
        height: 2.5vh;
        margin-right: 10px;
        color: var(--accent-color);
        transition: 0.5s;
    }
    li.nostyle:hover .icon{
        height: 3vh;
        margin-right: 7px;
    }
li.nostyle{
    list-style-type: none;
    display: flex;
    align-items: center;
    color: var(--accent-color);
    font-weight: 500;
    background-color: var(--background-color-highlight);
    transition: 0.5s;
}
li.nostyle:hover{
    background-color: var(--main-color);
}
  .header {
    background-color: var(--background-color-light);
    padding-bottom: 5vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .title {
    font-size: 25pt;
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
</style>
