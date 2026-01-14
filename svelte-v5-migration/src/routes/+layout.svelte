<script lang="ts">
  import '../app.css';
  import { fade } from 'svelte/transition';

  // Mock authentication store
  let isAuthenticated = $state(false);

  function login() {
    isAuthenticated = true;
  }

  function logout() {
    isAuthenticated = false;
  }
</script>

<header class="navbar">
  <div class="logo">
    <a href="/"><img src="/img/Logo.png" alt="GameON Logo"></a>
  </div>
  <nav class="nav-links">
    <ul>
      <li><a href="/">Головна</a></li>
      <li><a href="/catalog">Каталог</a></li>
      <li><a href="/feedback">Відгуки</a></li>
      <li><a href="/help">Підтримка</a></li>
      <li><a href="/cart" aria-label="Shopping Cart"><img src="/img/bag.png" alt="Shopping Cart"></a></li>
    </ul>
  </nav>
  <div class="auth-buttons">
    {#if isAuthenticated}
      <button class="login" onclick={logout}>Logout</button>
    {:else}
      <button class="login" onclick={login}>Login</button>
      <button class="register">Register</button>
    {/if}
  </div>
</header>

<main in:fade>
  <slot />
</main>

<div class="footer">
  <div>
    <h2>Про нас</h2>
  </div>
  <div>
    <h2>Магазин ігор</h2>
  </div>
  <div>
    <h2>Соціальні мережі</h2>
  </div>
</div>
<div class="footer1">
  <div>
    <p>GameHub - магазину ліцейзійних ігор для ПК, і не тільки. У нас ви можете купити ліцензійні копії найтоповіших ігор по самим низьким цінам!</p>
  </div>
  <div>
    <ul>
      <li><a href="/">Головна</a></li>
      <li><a href="/catalog">Каталог</a></li>
      <li><a href="/feedback">Відгуки</a></li>
      <li><a href="/help">Підтримка</a></li>
    </ul>
  </div>
  <div>
    <a href="https://www.tiktok.com/@mindogunlod?is_from_webapp=1&sender_device=pc" aria-label="TikTok"><img src="/img/tiktok.png" alt="TikTok"></a>
    <a href="https://www.instagram.com/mindogunlod/" aria-label="Instagram"><img src="/img/instagram.png" alt="Instagram"></a>
    <a href="/facebook" aria-label="Facebook"><img src="/img/facebook.png" alt="Facebook"></a>
  </div>
</div>
