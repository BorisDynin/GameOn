<script lang="ts">
  import { games } from '$lib/data';
</script>

<div class="content">
  <div class="aboutUS">
    <h1>GameON</h1>
    <p>Ласкаво просимо до GameON - магазину ліцейзійних ігор для ПК, і не тільки. У нас ви можете купити ліцензійні копії найтоповіших ігор по самим низьким цінам!</p>
    <ul><li><a href="/catalog">Каталог</a></li></ul>
  </div>
  <div class="game">
   <a href="/stalker2"><img src="/img/Stalker.png" alt="Stalker"></a>
  </div>
</div>
<div class="sale">
  {#each games as game}
    <div><a href="/{game.id}"><img src={game.images[0]} alt={game.name}></a></div>
  {/each}
</div>
