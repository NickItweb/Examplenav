<script>
  import {createEventDispatcher} from 'svelte'
  import Card from './Card.svelte'
  export let item

const dispatch = createEventDispatcher()

  const handleDelete =(itemId) => {
    dispatch('delete-feedback',itemId)
  }
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
  <button class="close" on:click={() => handleDelete(item.id)}>X</button>
  <p class="text-display">
    {item.text}  
  </p>
</Card>

<style>
  .num-display{
    position:absolute;
    top:-10px;
    left:-10px;
    width:20px;
    height:20px;
    text-align:center;
    padding:10px;
    background:red;
    color:#fff;
    border:1px #eee solid;
    border-radius:50%;

  }
  .close{
    position:absolute;
    top:10px;
    right:10px;
    cursor:pointer;
    font-size:20px ;
    font-weight:600;
  }
</style>