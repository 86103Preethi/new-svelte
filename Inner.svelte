<script>
import {createEventDispatcher} from 'svelte'


  const dispatch = createEventDispatcher()
  function greet() {   //2. define the greet function
      dispatch('greet','hello') //3.dispatch a event called greet with a data(hello)
  }
</script>

<main>
  <button on:click={greet}> Greet !</button> <!--1. we assign a funtion called greet-->
</main>
