<script lang="ts">
  import { Router, Route } from "svelte-navigator";
  import Home from "./pages/Home.svelte";
  import Album from "./pages/Album.svelte";
  import Navbar from "./components/Navbar.svelte";
  import NewAlbum from "./pages/NewAlbum.svelte";
  import Player from "./components/Player.svelte";
</script>

<Router>
    <Navbar />
    <Route path="/" primary={false} component={Home} />
    <Route path="/album/*id" primary={false} component={Album} />
    <Route path="/newalbum" primary={false} component={NewAlbum} />
    <Player />
</Router>
