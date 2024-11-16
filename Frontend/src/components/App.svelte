<script>
    import Header from './Header.svelte';
    import RegistrationForm from './RegistrationForm.svelte';
    import Dashboard from './components/Dashboard.svelte';
    import Events from './Events.svelte';
    import SupportMeasures from './SupportMeasures.svelte';
    import DevelopmentPath from './components/DevelopmentPath.svelte';
    
    let currentView = 'registration';

    function switchView(view) {
        currentView = view;
    }
</script>

<Header {switchView} />

<div class="container">
    {#if currentView === 'registration'}
        <RegistrationForm />
    {:else if currentView === 'dashboard'}
        <Dashboard />
    {:else if currentView === 'events'}
        <Events />
    {:else if currentView === 'support'}
        <SupportMeasures />
    {:else if currentView === 'development'}
        <DevelopmentPath />
    {/if}
</div>