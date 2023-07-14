<script>
 import {getContext} from 'svelte'

 //getcontext tp consume the value from the parent component
 const userName = getContext('username-context')
</script>



<main>
    <h2 class="text-center">
        Get the username from the App.svelte - <span class="text-blue-500 font-bold">{userName}</span>
      </h2>      
</main>