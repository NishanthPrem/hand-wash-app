<script>
import ProgressBar from "./ProgressBar.svelte";
    const totalSeconds = 5
    let secondsLeft = totalSeconds
    let isRunning = false
    $: progress = (totalSeconds - secondsLeft)/totalSeconds * 100

    function startTimer(){
        isRunning = true
        const timer = setInterval(() => {
        secondsLeft -=1
        if (secondsLeft ==0) {
            clearInterval(timer)
            isRunning = false
            secondsLeft = totalSeconds
        }
    }, 1000);
    }
</script>

<style>
    h2{
        margin: 0%;
    }
    .start{
        background-color: rgb(250, 93, 93);
        width: 100%;
        padding: 10px 0;
    }

    .start[disabled]{
        border: solid rgb(29, 23, 90) 1px;
        cursor: not-allowed;
    }

</style>

<div bp ='grid'>
    <h2 bp= "offset-5@md 4@md 12@sm">
        Seconds Left: {secondsLeft}
    </h2>
</div>

<ProgressBar {progress} />

<div bp ='grid'>
    <button 
    on:click = {startTimer} 
    disabled = {isRunning} 
    class="start" bp= "offset-5@md 4@md 12@sm">
    <span style="color: black"> START</span> 
    </button>
</div>