<script>
    import Feedbackitem from "./Feedbackitem.svelte";
    import {fade,scale} from 'svelte/transition';
    export let feedback=[];
</script>

{#each feedback as fb (fb.id) }
<div in:scale out:fade='{{duration:500}}'>
<Feedbackitem item={fb} on:delete-feedback/>
</div>
    
{/each}  