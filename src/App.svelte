<script>
    import Timmer from './components/Timmer.svelte';
    import HT from './components/HT.svelte'
    let audio;
    function timerEnds() {
        audio.play();
    }
</script>

<style>
	h1, h3 {
        text-align: center;
    }
</style>

<h1>Handwashing app</h1>
<Timmer on:end={timerEnds}/>
<HT />


<h3>
    <a href="https://phptuts.github.io/fcc-handwashing/handwashing.gif">
        Picture Source
    </a>
    <a href="https://freesound.org/people/metrostock99/sounds/345086/">
        Sound Source
    </a>
</h3>

<audio bind:this={audio}>
    <source src="sound.wav">
</audio>