<script>
  import Team from "./Team.svelte";

  let redScore = 20;
  let blueScore = 20;
  let winningText = "";

  $: redWon = blueScore === 0;
  $: blueWon = redScore === 0;
  $: gameOver = redWon || blueWon;

  $: btnText = gameOver ? "New Game" : "Reset score";
  $: btnCssClass = gameOver ? "btn-success" : "btn-warning";

  $: if (blueWon) {
    winningText = "Blue Won!";
  } else if (redWon) {
    winningText = "Red Won!";
  } else {
    winningText = "";
  }

  function newGame() {
    redScore = 20;
    blueScore = 20;
    btnText = "";
  }
</script>

<div class="row mt-2">
  <div class="col">
    <h1 class="text-center">MTG Counter</h1>
  </div>
</div>

<div class="row">
  <Team {gameOver} team="Red" bind:score={redScore} />
  <Team {gameOver} team="Blue" bind:score={blueScore} />
</div>

<div class="row mt-3">
  <div class="col">
    <button on:click={newGame} class="btn {btnCssClass} w-100">{btnText}</button
    >
  </div>
</div>

<div class="row mt-2">
  <h3 class="text-center">{winningText}</h3>
</div>
