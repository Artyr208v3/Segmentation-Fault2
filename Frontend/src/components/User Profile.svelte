<script>
  import Profile from './Profile.svelte';

  let userData = {
      name: 'Иван Иванов',
      email: 'ivan@example.com',
      bio: 'Разработчик программного обеспечения'
  };
</script>

<h1>Добро пожаловать, {userData.name}!</h1>
<Profile {userData} />