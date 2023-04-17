<script lang="ts">
    import UserMenu from "./UserMenu.svelte";
  let logged = false;
  export let onclick = () => {};
</script>

{#if !logged}
  <button
    id="wallet-btn"
    on:click={() => {
      onclick();
      logged = !logged;
    }}
  >
    Lens Login
  </button>
{:else}
  <button
    id="logged-wallet-btn"
    on:click={() => {
      onclick();
      logged = !logged;
    }}
  >
    <div class="image-cropper">
      <img id="lens-prof-pic" src="/heptagon.svg" alt="lens profile pic" />
    </div>
    {"User"}
  </button>
  <UserMenu class="user-menu"/>
{/if}

<style>
  #lens-prof-pic {
    height: 30px;
  }
  .image-cropper {
    width: 30px;
    height: 30px;
    position: relative;
    border-radius: 15px;
    overflow: hidden;
    margin-right: 5px;
  }
  #wallet-btn,
  #logged-wallet-btn {
    font-family: var(--lens-font);
    border-radius: 30px;
    box-sizing: border-box;
    border-width: 1px;
    border-color: var(--lens-color-dark);
    color: var(--lens-color-dark);
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    font-size: 1em;
    margin: 1vh 0;
    height: 45px;
    text-align: center;
    transition: all 300ms cubic-bezier(0.23, 1, 0.32, 1);
    user-select: none;
    touch-action: manipulation;
    will-change: transform;
    text-transform: uppercase;
    background-color: var(--lens-color-light);
    justify-content: center;
    width: 150px;
  }
  #wallet-btn:hover {
    color: var(--accent-color);
    border-color: var(--accent-color);
    box-shadow: rgba(0, 0, 0, 0.25) 0 8px 15px;
    transform: translateY(-2px);
  }
  #logged-wallet-btn {
    background-color: var(--background-color-light);
    border-color: var(--accent-color);
    color: var(--main-font-color);
    font-family: Avenir;
    text-transform: none;
  }
  #logged-wallet-btn+:global(.user-menu){
    display: none;
  }
  #logged-wallet-btn:hover+:global(.user-menu){
    display: block;
  }
</style>
