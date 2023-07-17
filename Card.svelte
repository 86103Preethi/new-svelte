
<main>
    <div>
    <slot>Default Content</slot>  
    </div>

    <div>
      <slot name='header'></slot> <!--multiple slots means 'name' has to be mentioned to let know the svelte-->
    </div>
    <div>
        <slot name='content'>Default Content</slot>
    </div>
    {#if $$slots.footer}   <!--if condition for hr tag will be displayed only if the footer is present-->
    <hr/>
    <div>
        <slot name='footer'></slot>
    </div>
    {/if}
</main>

<style>

</style>

