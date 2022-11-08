<script>
    export let style= 'primary';
export let type = 'button';
export let disabled = false;
</script>

<button {type} {disabled} class={style}>
    <slot></slot></button>

<style>
    button{
        color: #fff;
        border: 0;
        margin: 5px 0;
        padding: 20px 30px;
        position: absolute;
        outline: none;
        border-radius: 8px;
        color: #fff;
        transform: translateX(-100px);
        height: 50px;
        cursor: pointer;
    }
    .primary{
        background-color: #202142;
    }
    .secondary{
        background: #ff6a95;
    }
    button:hover{
       background-color: #333;
    }
    button:disabled{
        background-color: #cccccc;
        color: #333;
        cursor: auto;
    }
    button:disabled:hover{
        background-color: rgb(177, 151, 151);
    }
</style>