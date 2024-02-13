<script lang="ts">
    import Team from "./components/Team.svelte";
    import { TeamType } from "./helpers/enums";

    let blueScore = 20;
    let redScore = 20;

    $: redWon = blueScore === 0;
    $: blueWon = redScore === 0;
    $: gameOver = redWon || blueWon;

    function newGame() {
        blueScore = 20;
        redScore = 20;
    }
</script>

<div class="row mt-2">
    <div class="col">
        <h1 class="text-center">MTG Counter</h1>
    </div>
</div>

<div class="row">
    <Team
        team="Red"
        bind:score={redScore}
        teamType={TeamType.TeamA}
        {gameOver}
    />
    <Team
        team="Blue"
        bind:score={blueScore}
        teamType={TeamType.TeamB}
        {gameOver}
    />
</div>

<div class="row mt-3">
    <button on:click={newGame} class="btn btn-warning">Reset Game</button>
</div>
