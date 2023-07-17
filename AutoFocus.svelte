<script>
import {onMount}  from 'svelte'
let inputRef  //declare a varibale


onMount(() =>{
   inputRef.Focus()
})

</script>

<main>
    
   <input type ='text' bind:this={inputRef}/>    
</main>

<style>

</style>