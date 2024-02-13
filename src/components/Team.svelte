<script lang="ts">
    import { TeamType } from "../helpers/enums";

    export let team: string;
    export let score: number;
    export let teamType: TeamType;

    function add() {
        score += 1;
    }

    function sub() {
        score -= 1;
    }
</script>

<div style="border: dashed {team.toLowerCase()} 5px" class="col">
    <h2
        class:text-danger={teamType === TeamType.TeamA}
        class:text-primary={teamType === TeamType.TeamB}
    >
        Team {team}: {score}
    </h2>
    <button on:click={add} class="btn btn-success">+</button>
    <button on:click={sub} class="btn btn-danger">-</button>
</div>

<style>
    div.col {
        padding: 20px;
        text-align: center;
    }
</style>
