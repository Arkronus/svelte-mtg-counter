<script>
    export let team
    export let score
    export let gameOver;

    function plus() {
        score += 1
    }

    function minus() {
        score -= 1
    }
</script>

<div class="col" style="border:dashed {team.toLowerCase()} 5px;">
    <h2 class:text-danger={team === "Red"}
        class:text-primary={team === "Blue"}
    >Team {team}: {score}</h2>
    <button disabled={gameOver} on:click={plus} class="btn btn-success">+</button>
    <button disabled={gameOver} on:click={minus} class="btn btn-danger">-</button>
</div>

<style>
    div.col {
        padding: 20px;
        text-align: center;
    }
</style>