<script>
	import HowTo from "./HowTo.svelte"
	import Timer from "./Timer.svelte"

	let audio;

	function timerEnds(e){
		audio.play();
	}
</script>

<style>
	h1, 
	h3 {
		text-align: center;
		color: rgb(126, 162, 240);
	}
</style>

<h1>How To Handwash</h1>

<Timer on:end={timerEnds} />
<HowTo />

<h3>
    <a href="https://www.who.int/" >
        Picture Source
    </a> <br><br>
    <a href="https://www.who.int/" >
        Sound Source
    </a>
</h3>

<audio bind:this={audio}>
	<source src="Rome.mp3" type="audio/mpeg">
</audio>