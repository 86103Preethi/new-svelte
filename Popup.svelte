<script>
import {createEventDispatcher} from 'svelte'

const dispatch = createEventDispatcher() 


</script>


<main class="bg-white p-5 text-center">
     <h2 class="text-xl">This is a Popup</h2>
     <button 
     class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded mt-4"
     on:click={() => dispatch('close','Vishnu')}>Close Popup</button>   <!--dispatch= it can emit event by passing name and any event data  -->
</main>