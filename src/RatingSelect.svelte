<script>
   import {createEventDispatcher} from 'svelte';
   const dispatch = createEventDispatcher();
    let selected =10;
     const onchange = (e)=>{
      selected = e.currentTarget.value;
      dispatch('rating-select',selected)
     }

</script>

<ul class="rating">
 <li>
    <input type="radio" id="num1" value="1" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num1">1</label>
 </li>
 <li>
    <input type="radio" id="num2" value="2" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num2">2</label>
 </li>
 <li>
    <input type="radio" id="num3" value="3" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num3">3</label>
 </li>
 <li>
    <input type="radio" id="num4" value="4" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num4">4</label>
 </li>
 <li>
    <input type="radio" id="num5" value="5" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num5">5</label>
 </li>
 <li>
    <input type="radio" id="num6" value="6" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num6">6</label>
 </li>
 <li>
    <input type="radio" id="num7" value="7" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num7">7</label>
 </li>
 <li>
    <input type="radio" id="num8" value="8" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num8">8</label>
 </li>
 <li>
    <input type="radio" id="num9" value="9" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num9">9</label>
 </li>
 <li>
    <input type="radio" id="num10" value="10" name="rating" on:change={onchange} checked={selected===1} />
    <label for="num10">10</label>
 </li>
</ul>


<style>
    .rating{
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 30px 0;
    }
    .rating li{
        position: relative;
        background: #f4f4f4;
        width: 50px;
        height: 50px;
        padding: 10px;
        text-align: center;
        border-radius: 50%;
        font-size: 19px;
        border: 1px #eee solid;
        transition: 0.3s;
    }
    .rating li label{
        position: absolute;
        top: 50%;
        left: 50%;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        padding: 10px;
        transform: translate(-50%,-50%);
        cursor: pointer;
    }
    .rating li:hover{
        background: #ff6a95;
        color: #fff;
    }
    [type='radio']{
        opacity: 0;
    }

    [type='radio']:checked~label{
        background: #ff6a95;
        color: #fff;
    }
</style>