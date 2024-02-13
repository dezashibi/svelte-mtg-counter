<script lang="ts">
    export let gameOver: boolean;
    export let onClick: () => void;
</script>

{#if !gameOver}
    <button on:click={onClick} class="btn btn-warning w-100">
        Reset Game
    </button>
{:else}
    <button on:click={onClick} class="btn btn-success w-100"> New Game </button>
{/if}
