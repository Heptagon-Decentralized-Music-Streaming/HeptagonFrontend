<script lang="ts">
  import NewAlbumButton from "../components/NewAlbumButton.svelte";
  import MdDelete from "svelte-icons/md/MdDelete.svelte";
  import FaPlus from "svelte-icons/fa/FaPlus.svelte";
  import FaPlayCircle from "svelte-icons/fa/FaPlayCircle.svelte";
  import MdFileUpload from "svelte-icons/md/MdFileUpload.svelte";
  let songs = [];
  const addSong = (song) => {
    songs = songs.concat(song);
  };
  const deleteSong = (index) => {
    songs.splice(index, 1);
    songs = songs;
  };
</script>

<div class="album-header">
  <div class="album-cover-image">
    <NewAlbumButton />
  </div>
  <div class="album-header-text">
    <input class="title" placeholder="Title" />
    <input class="author-name" placeholder="Author" />
  </div>
  <div class="upload-container">
    <div class="icon upload">
      <MdFileUpload />
    </div>
    <span class="upload-desc">
        Upload Album</span>
  </div>
</div>
<div class="song-list-container">
  <ol class="song-list">
    {#each songs as song, index}
      <li class="song">
        <span class="song-edit-container">
          <input class="song-name-edit" placeholder="Untitled" />
          <div
            class="icon delete"
            on:click={() => deleteSong(index)}
            on:keyup={() => deleteSong(index)}
          >
            <MdDelete />
          </div>
          <div class="icon play">
            <FaPlayCircle />
          </div>
        </span>
      </li>
    {/each}
    <li
      class="song nostyle"
      on:click={() => addSong({})}
      on:keyup={() => addSong({})}
    >
      <div class="icon">
        <FaPlus />
      </div>
      Add track
    </li>
  </ol>
</div>

<style>
  .play {
    color: green;
  }
  .album-header {
    display: flex;
    background-color: var(--background-color-light);
    align-items: center;
    padding: 1vw;
    justify-content: left;
    padding-left: 15vw;
  }
  .album-header-text {
    text-align: left;
    padding: 3vw;
  }
  .title {
    font-size: 3.2em;
    line-height: 1.1;
    font-family: var(--main-font);
    display: block;
    border: none;
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
    background-color: transparent;
    border-bottom: 1px solid var(--accent-color);
  }
  .author-name {
    font-size: 16pt;
    font-family: var(--main-font);
    font-weight: 400;
    background-color: transparent;
    border: none;
    border-bottom: 1px solid var(--accent-color);
  }
  .song-list-container {
    margin-left: 18vw;
    margin-right: 18vw;
    text-align: left;
    font-size: 14pt;
  }
  .song-list {
    padding: 0;
  }
  .song {
    background-color: var(--background-color-light);
    padding: 0.5vh 1vw;
    list-style-position: inside;
    border: 1px solid var(--accent-color);
    border-bottom: none;
    transition: 0.2s;
  }
  .song-edit-container {
    display: flexbox;
    align-items: center;
  }
  .song-edit-container input {
    width: 90%;
  }
  input:focus {
    outline: none;
  }
  .song:last-of-type {
    border: 1px solid var(--accent-color);
  }
  .song:hover {
    background-color: var(--background-color-highlight);
  }
  .album-cover-image {
    margin: 0.5vw;
    aspect-ratio: 1/1;
    height: clamp(150px, 15vw, 15vw);
  }
  .icon {
    cursor: pointer;
    aspect-ratio: 1/1;
    vertical-align: middle;
    float: right;
    height: 22px;
    margin-right: 10px;
    color: var(--accent-color);
    transition: 0.5s;
  }
  .play {
    border-radius: 11px;
    color: rgb(0, 180, 0);
    transition: 0.1s;
  }
  .play:hover {
    box-shadow: 0 0 2px 2px rgb(0, 180, 0);
  }
  .play:active {
    opacity: 0.7;
  }
  .delete {
    color: rgb(255, 80, 80);
  }
  .upload {
    height: 60px;
    align-self: center;
    color: var(--background-color-light);
    background-color: var(--accent-color);
    border-radius: 30px;
    transition: 0.1s;
    margin: 0;
  }
  .upload:hover, .upload-container:hover .upload{
    box-shadow: 0 0 5px 5px var(--main-color);
  }
  .upload:active {
    opacity: 0.7;
    box-shadow: 0 0 5px 5px var(--main-color);
  }
  li.nostyle {
    cursor: pointer;
    list-style-type: none;
    justify-content: left;
    display: flex;
    align-items: center;
    color: var(--accent-color);
    font-weight: 500;
    background-color: var(--background-color-light);
  }
  .song-name-edit {
    font-family: var(--main-font);
    font-size: 14pt;
    background: none;
    border: none;
    margin: none;
  }
  .upload-container{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .upload-desc{
    margin-top: 10px;
    color: var(--accent-color);
    cursor: pointer;
  }
  .upload-desc:hover, .upload-container:hover .upload-desc{
    opacity: 0.7;
  }
</style>
