<script lang="ts">
  import { games } from '$lib/data';
  import { page } from '$app/stores';

  const game = games.find(g => g.id === $page.params.gameId);
</script>

{#if game}
  <div class="game-details">
    <h1>{game.name}</h1>
    <div class="game-images">
      {#each game.images as image}
        <img src={image} alt={game.name}>
      {/each}
    </div>
    <p>{game.description}</p>
    <p>{game.price}</p>
  </div>
{/if}
