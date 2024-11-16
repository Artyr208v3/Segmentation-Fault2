<script>
    export let userData = {
        name: '',
        age: '',
        achievements: []
    };
</script>

<h2>Личный кабинет</h2>
<p>Имя: {userData.name}</p>
<p>Возраст: {userData.age}</p>

<h3>Достижения</h3>
<ul>
    {#each userData.achievements as achievement}
        <li>{achievement}</li>
    {/each}
</ul>