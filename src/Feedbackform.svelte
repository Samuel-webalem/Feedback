<script>
  import {v4 as uuidv4} from 'uuid';
  import { createEventDispatcher } from 'svelte';
  import Card from "./card.svelte";
  import Button from "./button.svelte";
  import RatingSelect from "./RatingSelect.svelte";
  
  const dispatch = createEventDispatcher();
  let btndisabel = false;
  let text = "";
  let rating = 10;
  let min = 10;
  let messege;
  const handleinput = () => {
    if (text.trim().length <= min) {
      messege = `Text must be at least${min} characters`;
      btndisabel = true;
    } else {
      messege = null;
      btndisabel = false;
    }
  };
 
  const handleSelect = (e) => (rating = e.detail);
  const handlesubmit = ()=>{
    if(text.trim().length>min){
      const newfeedback = {
        id:uuidv4(),
        text,
        rating: +rating
      }
  
      dispatch('add-newfeedback',newfeedback)
    }
  }
</script>

<Card>
<header>
    <h2>How would you rate your service with us?</h2>
  </header>
  <form on:submit|preventDefault={handlesubmit}>
    <RatingSelect on:rating-select="{handleSelect}" />
    <div class="input-group">
      <input
        type="text"
        on:input="{handleinput}"
        bind:value="{text}"
        placeholder="Tell us something that keeps you coming again"
      />
      <Button disabled="{btndisabel}" type="submit">Send</Button>
    </div>
    {#if messege}
      <h3 class="messege">{messege}</h3>
    {/if}
  </form>
</Card>

<style>
  header {
    max-width: 400px;
    margin: auto;
    text-align: center;
  }
  form {
    text-align: center;
  }
  .messege {
    color: red;
  }
  input {
    margin: auto;
    width: 100%;
    outline: none;
    border-radius: 5px;
    height: 60px;
    font-size: 20px;
    padding: 10px;
  }
</style>
