<script>
    import Header from './components/Header.svelte';
    import RegistrationForm from './components/RegistrationForm.svelte';
    import Dashboard from './components/Dashboard.svelte';
    import Events from './components/Events.svelte';
    import SupportMeasures from './components/SupportMeasures.svelte';
    import DevelopmentPath from './components/DevelopmentPath.svelte';
    import Profile from './components/Profile.svelte';

    let currentView = 'registration';
    let userData = {
        name: '',
        email: '',
        age: '',
        bio: '',
        achievements: []
    };

    function switchView(view) {
        currentView = view;
    }

    function updateUser Data(data) {
        userData = { ...userData, ...data };
    }
</script>

<Header {switchView} />

<div class="container">
    {#if currentView === 'registration'}
        <RegistrationForm {updateUser Data} />
    {:else if currentView === 'dashboard'}
        <Dashboard {userData} />
    {:else if currentView === 'events'}
        <Events />
    {:else if currentView === 'support'}
        <SupportMeasures />
    {:else if currentView === 'development'}
        <DevelopmentPath />
    {:else if currentView === 'profile'}
        <Profile {userData} {updateUser Data} />
    {/if}
</div>