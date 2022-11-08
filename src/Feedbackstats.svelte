<script>
    export let average;
    export let count;
    if(!average)
    {
        average='0'
    }
</script>

<div class="feedbackstats">
    <h4>{count} Reviews</h4>
    
    <h4>Average Ratings: {average}</h4>
</div>

<style>
    .feedbackstats{
        display: flex;
        justify-content: space-between;
    }
</style>