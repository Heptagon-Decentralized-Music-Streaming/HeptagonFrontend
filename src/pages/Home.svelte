<script lang="ts">
  import { text } from "svelte/internal";
  let albums = [
    {
      title: "The Godfather Soundtrack",
      cover:
        "https://source.boomplaymusic.com/group10/M00/11/18/e84753221e1f48859b67e0b4ba3bc927_320_320.jpg",
    },
    {
        title: "Happy Together",
        cover:
            "https://upload.wikimedia.org/wikipedia/en/4/47/Turtleshappytogether.jpg"
    },
    {
        title: "Happy Together",
        cover:
            "https://upload.wikimedia.org/wikipedia/en/4/47/Turtleshappytogether.jpg"
    },
    {
        title: "Happy Together",
        cover:
            "https://upload.wikimedia.org/wikipedia/en/4/47/Turtleshappytogether.jpg"
    },
    {
        title: "Happy Together",
        cover:
            "https://upload.wikimedia.org/wikipedia/en/4/47/Turtleshappytogether.jpg"
    },
    {
        title: "Happy Together",
        cover:
            "https://upload.wikimedia.org/wikipedia/en/4/47/Turtleshappytogether.jpg"
    }
  ];
</script>

<main>
  <h1 class="page-title">Decentralized Music Streaming</h1>
  <input class="search-bar" placeholder="Find new music..." />
  <h2 class="page-title">Recommended</h2>
  <div class="album-list">
    {#each albums as album, index}
      <div class="album-cover">
        <img
          class="album-cover-image"
          alt="album-1"
          src={album.cover}
        />
        <span class="album-title">{album.title}</span>
      </div>
    {/each}
  </div>
</main>

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
    box-shadow: 0px 0px 5px 5px rgb(50, 0, 100);
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
