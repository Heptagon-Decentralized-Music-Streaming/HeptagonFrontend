<script lang="ts">
  export let min = 0;
  export let max = 1;
  export let value;
  export let step = 0.01;
</script>

<div class="progress-bar-container">
  <div class="h-2 w-full rounded-sm bg-purple-300 absolute" />
  <div
    class="h-2 rounded-sm bg-gradient-to-r from-purple-300 to-purple-500 absolute"
    style={`width: ${(value * 100) / max}%;`}
  />
  <input
    bind:value
    {min}
    {max}
    {step}
    type="range"
    class="progress-background"
  />
</div>

<style>
  .progress-background{
    width: 100%;
  }
  .progress-bar-container{
    width: 100%;
    align-items: center;
  }
</style>
