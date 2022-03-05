<script>
    export let progress = 70
</script>
<style>
    .progress-container {
        margin: 10px 0;
        border: solid rgb(194, 194, 194) 1px;
    }

    .progress-bar {
        background-color: rgba(166, 243, 166, 0.932);
        height: 30px;
    }

    .sr-only {
        color:rgb(2, 2, 2);
    }
</style>

<div bp = "grid">
    <div bp= "offset-5@md 4@md 12@sm" 
    class="progress-container">
    <div class="progress-bar" style = "width: {progress}%">
        <span class="sr-only">%{progress}</span>
    </div>
    </div>

</div>