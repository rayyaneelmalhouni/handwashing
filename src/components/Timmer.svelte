<script>
    import Progress from './Progress.svelte';
    const totalSeconds = 20;
    $: progression = ((totalSeconds - secondLeft) / totalSeconds) * 100;
    let secondLeft = totalSeconds;
    let isRunning = false;
    function startButton() {
        isRunning = true;
        let interval = setInterval(() => {
                secondLeft -= 1
            
            if (secondLeft == 0) {
                clearInterval(interval);
                isRunning = false;
                secondLeft = totalSeconds;
            }
        }, 1000);
    }
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

    .start[disabled] {
        background-color:  rgb(194, 194, 194);
        cursor: not-allowed;
    }
</style>
<div bp ="grid">
    <h2 bp="offset-5@md 4@md 12sm">Seconds Left: {secondLeft}</h2>
</div>

<Progress {progression}/>
<div bp="grid">
<button bp="offset-5@md 4@md 12@sm" class="start" disabled={isRunning} on:click={startButton}>Start</button>
</div>