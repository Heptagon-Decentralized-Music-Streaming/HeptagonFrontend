<script lang="ts">
    import { link } from "svelte-navigator";
    import { AudioPlayer } from 'svelte-audio-player'
    import PurplePlayer from "./player/PurplePlayer.svelte";
</script>
  
  <div id="hept-player">
    <AudioPlayer src="/godfather.mp3">
        <PurplePlayer/>
    </AudioPlayer>
  </div>
  <div id="hept-player-placeholder"/>
  
  <style>
    #hept-player {
      position: fixed;
      left: 0;
      align-items: center;
      bottom: 0;
      width: 100%;
      height: clamp(100px,15vh,15vh);
      background-color: #6400c8;
    }
    #hept-player-placeholder{
      width: 100%;
      height: clamp(100px,15vh,15vh);
    }
  </style>