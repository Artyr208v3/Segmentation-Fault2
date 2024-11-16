<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();
    export let userData;
    export let updateUser Data;

    let isEditing = false;

    function toggleEdit() {
        isEditing = !isEditing;
    }

    function saveProfile() {
        
        toggleEdit();
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
            <input type="date" bind:value={userData.date} />
        </label>
        <label>
            Место обучения:
            <input bind:value={userData.teach} />
        </label>
        <label>
            Номер телефона:
            <input type="tel" bind:value={userData.number} />
        </label>
        <label>
            Email:
            <input type="email" bind:value={userData.email} />
        </label>
        <label>
            Направление:
            <input bind:value={userData.naprav} />
        </label>
        <button on:click={saveProfile}>Сохранить</button>
        <button on:click={toggleEdit}>Отмена</button>
    </div>
{:else}
    <div>
        <p><strong>ФИО:</strong> {userData.name}</p>
        <p><strong>Дата рождения:</strong> {userData.date}</p>
        <p><strong>Место обучения:</strong> {userData.teach}</p>
        <p><strong>Номер телефона:</strong> {userData.number}</p>
        <p><strong>Email:</strong> {userData.email}</p>
        <p><strong>Направление:</strong> {userData.naprav}</p>
        <button on:click={toggleEdit}>Редактировать</button>
    </div>
{/if}