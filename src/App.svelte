<script lang="ts">
    import Team from "./components/Team.svelte";
    import { TeamType } from "./helpers/enums";

    let blueScore = 20;
    let redScore = 20;
</script>

<div class="row mt-2">
    <div class="col">
        <h1 class="text-center">MTG Counter</h1>
    </div>
</div>

<dov class="row">
    <Team team="Red" bind:score={redScore} teamType={TeamType.TeamA} />
    <Team team="Blue" bind:score={blueScore} teamType={TeamType.TeamB} />
</dov>
