<script lang="ts">
  import PauseIcon from "./icons/PauseIcon.svelte";
  import PlayIcon from "./icons/PlayIcon.svelte";
  import RepeatIcon from "./icons/RepeatIcon.svelte";
  import RewindIcon from "./icons/RewindIcon.svelte";
  import SpeedIcon from "./icons/SpeedIcon.svelte";
  import { getAudioContext } from "svelte-audio-player";
  import { toggle, toHHMMSS } from "svelte-audio-player/utils";
  import RangeSlider from "./RangeSlider.svelte";
  import VolumeControl from "./VolumeControl.svelte";
  const SEEK_SECONDS = 10;
  const PLAYBACK_SPEEDS = [1, 1.25, 1.5, 1.75, 2, 0.25, 0.5, 0.75];
  const {
    playing,
    playbackRate,
    paused,
    repeat,
    seekBy,
    currentTime,
    duration,
  } = getAudioContext();
  let speedIndex = 0;
  const handlePlaybackSpeedClick = () => {
    $playbackRate = PLAYBACK_SPEEDS[++speedIndex % PLAYBACK_SPEEDS.length];
  };
</script>

<div
  class="player-container"
>
  <div  class="button-container">
    <button class="icon" on:click={() => toggle(repeat)}>
      <RepeatIcon
        class="icon"
      />
    </button>

    <button class="icon" on:click={() => seekBy(-1 * SEEK_SECONDS)}>
      <RewindIcon />
    </button>
    <button
      on:click={() => toggle(paused)}
      class="icon"
    >
      {#if $playing}
        <PauseIcon />
      {:else}
        <PlayIcon />
      {/if}
    </button>

    <button class="icon" on:click={() => seekBy(SEEK_SECONDS)}>
      <SpeedIcon />
    </button>

    <button
    class="icon"
      on:click={handlePlaybackSpeedClick}
    >
      <span class="text-[8px] font-semibold text-white">{$playbackRate}x</span>
    </button>
  </div>

  <div class="progress-bar">
    <span class="timer">{toHHMMSS($currentTime)}</span>
    <div class="progress-slider">
    <RangeSlider max={$duration} bind:value={$currentTime} />
    </div>
    <span class="timer">{toHHMMSS($duration)}</span>
    <VolumeControl />
  </div>
</div>

<style>
  .player-container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .button-container{
    padding: 2vh;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
  }
  .icon{
    background-color: rgb(60, 0, 120,0.9);
    width: 3rem;
    height: 3rem;
    border-radius: 99999px;
    justify-content: center;
    align-items: center;
    display: flex;
    padding: 0 0;
  }
  .progress-bar{
    display: flex;
    align-items: center;
  }
  .progress-slider{
    width: 40vw;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .timer{
    margin: 0 0.5vw;
  }
</style>
