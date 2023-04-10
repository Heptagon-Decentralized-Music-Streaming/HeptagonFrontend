<script lang="ts">
  import { Router, Route } from "svelte-navigator";
  import Home from "./pages/Home.svelte";
  import Navbar from "./components/Navbar.svelte";
  import Player from "./components/Player.svelte";
</script>

<Router>
    <Navbar />
    <Route path="/" primary={false} component={Home} />
    <Player />
</Router>

<style>
  main {
    height: 100%;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>