<script>
  export let switchView;
</script>

<header>
  <h1>MVP Система</h1>
  <nav>
    <ul>
      <button href="#registration" on:click={() => switchView('registration')}>Регистрация</button>
      <button href="#dashboard" on:click={() => switchView('dashboard')}>Личный кабинет</button>
      <button href="#events" on:click={() => switchView('events')}>Мероприятия</button>
      <button href="#support" on:click={() => switchView('support')}>Поддержка</button>
      <button href="#registration" on:click={() => switchView('development')}>На взлёт!</button>
    </ul>
  </nav>
</header>