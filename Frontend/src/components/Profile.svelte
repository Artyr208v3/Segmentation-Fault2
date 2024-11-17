<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();
    export let userData;

    userData = {
        name: "", 
        data: "",
        
    }
</script>

<h2>Профиль пользователя</h2>

{#if isEditing}
    <div>
        <label>
            ФИО:
            <input bind:value={userData.name} />
        </label>
        <label>
            Дата рождения:
            <input bind:value={userData.name} />
        </label>
        <label>
            Место обучения:
            <input bind:value={userData.name} />
        </label>
        <label>
            Номер телефона:
            <input bind:value={userData.name} />
        </label>
        <label>
            Email:
            <input bind:value={userData.name} />
        </label>
        <label>
            Направление:
            <input bind:value={userData.name} />
        </label>
        <button on:click={saveProfile}>Сохранить</button>
        <button on:click={toggleEdit}>Отмена</button>
    </div>
{:else}
    <div>
        <p><strong>ФИО:</strong> {userData.name}</p>
        <p><strong>Дата рождения:</strong> {userData.email}</p>
        <p><strong>Место обучения:</strong> {userData.bio}</p>
        <p><strong>Номер телефона:</strong> {userData.name}</p>
        <p><strong>Email:</strong> {userData.email}</p>
        <p><strong>Направление:</strong> {userData.bio}</p>
        <button on:click={toggleEdit}>Редактировать</button>
    </div>
{/if}