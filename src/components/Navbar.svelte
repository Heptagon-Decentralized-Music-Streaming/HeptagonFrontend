<script lang="ts">
  import { link } from "svelte-navigator";
  import LogInButton from "./LogInButton.svelte";
</script>

<div id="navbar-placeholder"/>
<div id="navbar">
  <a use:link href="/" id="homepage-link">
    <div class="hept-title">
      <img height="50px" alt="heptagon_logo" src="/heptagon.svg" />
      <span class="hept-title-text">Heptagon</span>
    </div>
  </a>
  <div id="navbar-links">
    <a class="navbar-link" use:link href="/info">Info</a>
    <a class="navbar-link" use:link href="/blog">Blog</a>
    <a class="navbar-link" use:link href="/contact">Contact</a>
    <LogInButton />
  </div>
</div>

<style>
  #navbar-placeholder{
    width: 100%;
    height: clamp(70px, 10vh, 10vh);
  }
  .hept-title {
    display: flex;
    align-items: center;
  }
  .hept-title-text {
    margin-left: 5px;
    margin-top: 10px;
    font-weight: 500;
  }
  #navbar {
    position: fixed;
    display: flex;
    justify-content: space-between;
    left: 0;
    align-items: center;
    top: 0;
    width: 100%;
    height: clamp(70px, 10vh, 10vh);
    background-color: var(--main-color);
    border-bottom: 1px solid var(--accent-color);
  }
  #homepage-link,
  #homepage-link:hover {
    position: relative;
    text-decoration: none;
    margin: 2vw;
    padding: 1vh;
    font-weight: 100;
    font-size: 150%;
    color: #ffffff;
  }
  #navbar-links {
    display: flex;
    position: relative;
    align-items: center;
    margin-right: 2vw;
  }
  .navbar-link,
  .navbar-link:hover {
    font-weight: 100;
    font-size: 120%;
    padding: 1vw;
  }
  .navbar-link:hover {
    text-decoration: none;
    opacity: 50%;
    transition: 0.2s;
  }
  @media only screen and (max-width: 600px) {
    .navbar-link {
      display: none;
    }
  }
</style>
