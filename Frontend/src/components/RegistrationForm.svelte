<script>
    let username = '';
    let email = '';
    let password = '';
  
    function handleSubmit() {
      console.log({ username, email, password });
    }
  </script>
  
  <form on:submit|preventDefault={handleSubmit}>
    <h2>Регистрация</h2>
    <label>
      <input type="text" bind:value={username} placeholder="Имя пользователя" required />
    </label>
    <label>
      <input type="email" bind:value={email} placeholder="Email" required />
    </label>
    <label>
      <input type="password" bind:value={password} placeholder="Пароль" required />
    </label>
    <label>
      <button type="submit">Зарегистрироваться</button>
    </label>
  </form>
  
  <style>
    
  </style>