<script>
    import Header from './components/Header.svelte';
    import RegistrationForm from './components/RegistrationForm.svelte';
    import User_Profile from './components/User_Profile.svelte';
    import Events from './components/Events.svelte';
    import SupportMeasures from './components/SupportMeasures.svelte';
    import DevelopmentPath from './components/DevelopmentPath.svelte';
    import Profile from './components/Profile.svelte';

    let currentView = 'registration';
    let userData = {
        name: '',
        email: '',
        name = '',
        data = '',
        teach = '',
        number = '',
        email = '',
        naprav = '',
        achievements: []
    };

    function switchView(view) {
        currentView = view;
    }

    function updateUser_Data(data) {
        userData = { ...userData, ...data };
    }
</script>

<Header {switchView} />

<div class="container">
    {#if currentView === 'registration'}
        <RegistrationForm {updateUser_Data} />
    {:else if currentView === 'dashboard'}
        <User_Profile {userData} />
    {:else if currentView === 'events'}
        <Events />
    {:else if currentView === 'support'}
        <SupportMeasures />
    {:else if currentView === 'development'}
        <DevelopmentPath />
    {:else if currentView === 'profile'}
        <Profile {userData} {updateUser_Data} />
    {/if}
</div>