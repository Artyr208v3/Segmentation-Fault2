<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  let name = '';
  let data = '';
  let teach = '';
  let number = '';
  let email = '';
  let naprav = '';
  let errorMessage = '';

  function handleSubmit() {
      if (!name || !data || !teach || !number || !email || !naprav) {
          errorMessage = 'Пожалуйста, заполните все поля.';
          return;
      }
      if (data < 18) {
          errorMessage = 'Возраст должен быть 18 лет или старше.';
          return;
      }
      errorMessage = '';
      dispatch('updateUser Data', { name, email, teach, number, email, naprav });
      // Здесь можно добавить логику для отправки данных на сервер
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <h2>Регистрация</h2>
  {#if errorMessage}
      <p class="p-100">{errorMessage}</p>
  {/if}
  <label>
      ФИО:
      <input type="text" bind:value={name} required />
  </label>
  <label>
      Дата рождения:
      <input type="data" bind:value={data} required />
  </label>
  <label>
      Место обучения:
      <input type="teach" bind:value={teach} required />
  </label>
  <label>
      Номер:
      <input type="number" bind:value={number} required />
  </label>
  <label>
      Email:
      <input type="email" bind:value={email} required />
  </label>
  <label>
    Направление:
    <input type="naprav" bind:value={naprav} required />
</label>
  <button type="submit">Зарегистрироваться</button>
</form>

<style lang="postcss">
</style>