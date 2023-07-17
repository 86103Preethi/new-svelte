<script>
const name = [
        {fName:'Priya',
          lName:'ravi',
        },
        {fName:'Preethi',
        lName:'Kumar',
        },
        {fName:'Sandhiya',
        lName:'ilangovan',
         },
    ]
</script>



<main>
    {#each name as name (name)}
      <slot name='hero' firstName={name.fName} lastName={name.lName}/>  <!--assigning props-->
    {/each}
</main>