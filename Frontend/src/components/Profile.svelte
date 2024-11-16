<script>
    export let user = {
        name: '',
        email: '',
        bio: ''
    };

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
            Имя:
            <input type="text" bind:value={user.name} />
        </label>
        <label>
            Email:
            <input type="email" bind:value={user.email} />
        </label>
        <label>
            О себе:
            <textarea bind:value={user.bio}></textarea>
        </label>
        <button on:click={saveProfile}>Сохранить</button>
        <button on:click={toggleEdit}>Отмена</button>
    </div>
{:else}
    <div>
        <p><strong>Имя:</strong> {user.name}</p>
        <p><strong>Email:</strong> {user.email}</p>
        <p><strong>О себе:</strong> {user.bio}</p>
        <button on:click={toggleEdit}>Редактировать</button>
    </div>
{/if}