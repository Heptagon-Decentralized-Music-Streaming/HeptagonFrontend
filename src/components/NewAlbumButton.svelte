<script>
    import FaPlus from 'svelte-icons/fa/FaPlus.svelte'
</script>
<div class="new-album-btn">
    <div class="icon"><FaPlus></FaPlus></div>
</div>
<style>
    .icon{
        width: 50%;
        aspect-ratio: 1/1;
    }
    .new-album-btn{
        aspect-ratio : 1 / 1;
        color: var(--accent-color);
        background-color: var(--background-color-highlight);
        border: 4px dashed var(--accent-color);
        border-radius: 20px;
        padding: 3vw;
        transition: 0.2s;
        display: grid;
        align-items: center;
        justify-items: center;
    }
    .new-album-btn:hover{
        color: var(--accent-color);
        background-color: var(--main-color);
        box-shadow: 0px 0px 10px 10px var(--background-color-highlight);;
        border: 4px dashed var(--accent-color);
        padding: 3vw;
        cursor: pointer;
    }
</style>