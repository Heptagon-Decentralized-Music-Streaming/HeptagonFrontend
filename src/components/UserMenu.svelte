<script lang="ts">
  import { link } from "svelte-navigator";
</script>

<div class="menu {$$props.class}">
  <ul class="option-list">
    <li>
      <a use:link href="/profile"> Profile </a>
    </li>
    <li>
        <a use:link href="/newalbum"> New Album </a>
    </li>
    <li>
        <a use:link href="/library">My Library</a>
    </li>
    <li><a use:link href="/settings">Settings</a></li>
    <li><a use:link href="/profile">Log Out</a></li>
  </ul>
</div>

<style>
  .menu:hover {
    display: block !important;
  }
  .menu {
    position: absolute;
    top: 54px;
    right: 5px;
    background-color: var(--background-color-light);
    border-radius: 10px;
    width: 140px;
  }
  .option-list {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  .option-list > li {
    border-top: 1px solid var(--accent-color);
    padding: 5px 0;
  }
  .option-list > li:hover {
    background-color: var(--background-color-highlight);
    cursor: pointer;
  }
  .option-list > li:first-of-type {
    border-top-right-radius: 10px;
    border-top-left-radius: 10px;
    border-top: none;
  }
  .option-list > li:last-of-type {
    border-bottom-right-radius: 10px;
    border-bottom-left-radius: 10px;
    border-bottom: none;
  }
  .option-list > li > :global(a){
    color: var(--main-font-color)
  }
</style>
