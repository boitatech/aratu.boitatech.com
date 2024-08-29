<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();
    let selectedDate = '24.09.2024';

    function selectDate(date) {
        selectedDate = date;
        dispatch('dateSelected', { date });
    }
</script>

<style>
    @import './index.css'; 
</style>

<div class="buttons-container">
    <button 
        class:selected={selectedDate === '24.09.2024'} 
        on:click={() => selectDate('24.09.2024')}>
        Dia 24
    </button>
    <button 
        class:selected={selectedDate === '25.09.2024'} 
        on:click={() => selectDate('25.09.2024')}>
        Dia 25
    </button>
    <button 
        class:selected={selectedDate === '26.09.2024'} 
        on:click={() => selectDate('26.09.2024')}>
        Dia 26
    </button>
</div>
