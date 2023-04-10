<script lang="ts">
    export let onclick = ()=>{};
</script>
<button id="wallet-btn" on:click={onclick}>
    Lens Login
</button>
<style>
    #wallet-btn {
    font-family: "Space Grotesk";
    border-radius: 30px;
    box-sizing: border-box;
    border-width: 2px;
    border-color: rgb(0, 80, 3);
    color: rgb(0, 80, 30);
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    font-size: 1em;
    line-height: normal;
    margin: 1vh 0;
    height: 45px;
    text-align: center;
    transition: all 300ms cubic-bezier(0.23, 1, 0.32, 1);
    user-select: none;
    justify-self: center;
    touch-action: manipulation;
    will-change: transform;
    text-transform: uppercase;
    background-color: rgb(171, 254, 44);
    justify-content: center;
  }
  #wallet-btn:hover {
    color: rgb(128, 0, 255);
    border-color: rgb(128, 0, 255);
    box-shadow: rgba(0, 0, 0, 0.25) 0 8px 15px;
    transform: translateY(-2px);
  }
</style>