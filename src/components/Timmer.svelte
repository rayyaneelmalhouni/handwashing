<script>
    import Progress from './Progress.svelte';
</script>
<style>
    h2 {
        margin: 0;
    }
    .start {
        background-color: rgb(154, 73, 73);
        width: 100%;
        margin: 10px 0;

    }
</style>
<div bp ="grid">
    <h2 bp="offset-5@md 4@md 12sm">Seconds Left: </h2>
</div>
<Progress />
<button class="start">Start</button>