<script lang="ts">
  import { games } from '$lib/data';

  let searchTerm = $state('');

  const filteredGames = $derived(
    games.filter(game =>
      game.name.toLowerCase().includes(searchTerm.toLowerCase())
    )
  );
</script>

<div class="search-bar">
  <input type="text" bind:value={searchTerm} placeholder="Search for a game...">
</div>

<div class="conteiner">
  {#each filteredGames as game}
    <div class="colum">
      <img src={game.images[0]} alt={game.name} width="100%">
      <div class="row">
        <a href="/{game.id}">
          <img src={game.icon} alt="Посилання на товар" width="100%">
        </a>
        <p>
          <a href="/{game.id}">
            {game.price}
          </a>
        </p>
      </div>
    </div>
  {/each}
</div>
