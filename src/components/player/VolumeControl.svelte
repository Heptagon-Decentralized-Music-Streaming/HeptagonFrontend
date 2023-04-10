<script lang="ts">
  import VolumeMute from './icons/VolumeMute.svelte';
  import VolumeUp from './icons/VolumeUp.svelte';
  import RangeSlider from './RangeSlider.svelte';

  import { getAudioContext } from "svelte-audio-player";
  import { toggle } from "svelte-audio-player/utils";

  const { volume, muted } = getAudioContext();

  let volumePercentage = 100;
  $: $volume = volumePercentage / 100;
</script>

<div class="volume-button">
  <button class="volume-icon" on:click={() => toggle(muted)}>
    {#if $muted}
      <VolumeMute />
    {:else}
      <VolumeUp  />
    {/if}
  </button>

  <div class="volume-control">
    <RangeSlider bind:value={volumePercentage} max={100} step={1} />
  </div>
</div>

<style>
  .volume-icon{
    justify-content: center;
    align-items: center;
    display: flex;
    padding: 0 0;
    background: none;
    width: 1.5rem;
    height: 1.5rem;
  }
  .volume-button{
    justify-content: center;
    display: flex;
    flex-direction: column-reverse;
  }
  .volume-control{
    display: none;
    width: 5rem;
    height: 2rem;
    transform: rotate(-90deg) translate(50px,-22px) ;
    position: absolute;
  }
  .volume-icon:hover+.volume-control,.volume-control:hover{
    display: flex;
  }
</style>
