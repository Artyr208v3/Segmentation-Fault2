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
        // 
        updateUser Data({ name: userData.name, email: userData.email, bio: userData.bio });
        toggleEdit();
    }
</script>

<h2>Профиль пользователя</h2>

{#if isEditing}
    <div>
        <label>
            ФИО:
            <input type="text" bind:value={userData.name} />
        </label>
        <label>
            Дата рождения:
            <input type="email" bind:value={userData.email} />
        </label>
        <label>
            Место обучения:
            <input bind:value={userData.bio}></input>
        </label>
        <label>
            Номер телефона:
            <input type="text" bind:value={userData.name} />
        </label>
        <label>
            Email:
            <input type="text" bind:value={userData.name} />
        </label>
        <label>
            Направление:
            <input type="text" bind:value={userData.name} />
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