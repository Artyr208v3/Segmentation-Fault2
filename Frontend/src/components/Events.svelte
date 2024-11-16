<script>
    let events = [
        { title: 'Вебинар по Svelte', date: '2024-11-20' },
        { title: 'Конференция по IT', date: '2024-12-05' },
        { title: 'Хакатон по разработке', date: '2024-12-15' }
    ];
</script>

<h2>Актуальные мероприятия</h2>
<ul>
    {#each events as event}
        <li>{event.title} - {event.date}</li>
    {/each}
</ul>