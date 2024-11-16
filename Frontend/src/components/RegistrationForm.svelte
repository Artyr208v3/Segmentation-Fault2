<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  let name = '';
  let email = '';
  let age = '';
  let errorMessage = '';

  function handleSubmit() {
      if (!name || !email || !age) {
          errorMessage = 'Пожалуйста, заполните все поля.';
          return;
      }
      if (age < 18) {
          errorMessage = 'Возраст должен быть 18 лет или старше.';
          return;
      }
      errorMessage = '';
      dispatch('updateUser Data', { name, email, age });
      // Здесь можно добавить логику для отправки данных на сервер
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <h2>Регистрация</h2>
  {#if errorMessage}
      <p style="color: red;">{errorMessage}</p>
  {/if}
  <label>
      Имя:
      <input type="text" bind:value={name} required />
  </label>
  <label>
      Email:
      <input type="email" bind:value={email} required />
  </label>
  <label>
      Возраст:
      <input type="number" bind:value={age} required />
  </label>
  <button type="submit">Зарегистрироваться</button>
</form>