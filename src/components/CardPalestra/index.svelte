<script>
    export let event;
</script>

<style>
    @import './index.css';
</style>

<div class="card-content">
    <div class="dotted-line"></div>
    <p class="small">{event.date}, {event.time}</p>
    <h1 class="large">{event.topic}</h1>
    <h2 class="medium">{event.speaker}</h2>
    <p class="small desc-container">
        {event.description}
    </p>
</div>