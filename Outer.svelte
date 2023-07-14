<script>
  import Inner from "./Inner.svelte";


</script>

<main>
   <Inner on:greet/>  <!--greet handler =if we dont assign any handler, it will forward the event to the parent comp -->
</main>