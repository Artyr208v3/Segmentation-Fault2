<script>
  export let userData;
</script>

<h2>Профиль пользователя</h2>
<div>
  <p><strong>ФИО:</strong> {userData.name}</p>
  <p><strong>Дата рождения:</strong> {userData.date}</p>
  <p><strong>Место обучения:</strong> {userData.teach}</p>
  <p><strong>Номер телефона:</strong> {userData.number}</p>
  <p><strong>Email:</strong> {userData.email}</p>
  <p><strong>Направление:</strong> {userData.naprav}</p>
</div>