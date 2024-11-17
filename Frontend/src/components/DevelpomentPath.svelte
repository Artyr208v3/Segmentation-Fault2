<script>
    let goals = [];
    let newGoal = '';

    function addGoal() {
        if (newGoal) {
            goals.push(newGoal);
            newGoal = '';
        }
    }

    function removeGoal(index) {
        goals.splice(index, 1);
    }
</script>

<h2>На взлёт!</h2>
<input type="text" bind:value={newGoal} placeholder="Введите цель" />
<button on:click={addGoal}>Добавить цель</button>

<h3>Ваши цели</h3>
<ul>
    {#each goals as goal, index}
        <li>
            {goal} <button on:click={() => removeGoal(index)}>Удалить</button>
        </li>
    {/each}
</ul>