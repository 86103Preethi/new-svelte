<script>
    let name = "Preethi";
    const channel = "<b>convolution<b/>";
    const hack = `<a href="#" onclick="alert('u r hacked!')">Win a prize<a/>`;
    const id = "heading";
    const disabled = true;
    const status = "safe";
    const isPromoted = false;
    const num = "hi";
    const names = ["bruce", "lia", "diana"];
  
    // list and keys
    const fullnames = [
      { first: "Preethi", last: "Mark" },
      { first: "siva", last: "P" },
      { first: "Amala", last: "joseph" },
    ];
  
    //event handling
    let count = 0;
  
    function handleClick(event, stepSize) {
      //() inside is called parameter
      count += stepSize;
    }
</script>

<main>
    <h2 class="underline text-center">Underline text</h2>
    <h2 class={`${status === "danger" ? "threat" : "safe"}`}>Status</h2>
    <h1 class="text-red-800">Hello {name}!</h1>
    <p>{@html channel}</p>
    <div>{@html hack}</div>
    <div {id} class="bg-blue-200 p-4">This is heading</div>
    <button
      class={`${
        disabled
          ? "opacity-50 cursor-not-allowed"
          : "bg-green-500 text-white py-2 px-4 rounded"
      } `}>Bind</button
    >
    <h2 class={`${isPromoted ? "promoted" : "notpromoted"} `}>Movie</h2>
    <div class="font-bold text-purple-300">
      {#if num === 0}
        <h2>The number is Zero</h2>
      {:else if num < 0}
        <h2>negative</h2>
      {:else if num > 0}
        <h2>positive</h2>
      {:else}
        <h2>not a number</h2>
      {/if}
    </div>
  
    <div class="mb-10">
      {#each names as name, index}
        <h2>{index + 1} {name}</h2>
      {/each}
    </div>
  
    <div class="font-bold">
      {#each fullnames as name, index (name.first)}
        <h2>{index + 1}, {name.first} {name.last}</h2>
      {/each}
    </div>
  
    <div class="flex justify-center items-center mt-10">
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-t border-black-700"
        on:click={() => (count += 1)}>count {count}</button
      >
      <div>
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-t border-black-700"
          on:click={(event) => handleClick(event, 5)}>count {count}</button
        >
        <!--this arrow fun will automatically receive the event object as argument-->
      </div>
      <div>
        <button
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-t border-black-700"
          on:click={(event) => handleClick(event, 10)}>count {count}</button
        >
        <!--this arrow fun will automatically receive the event object as argument-->
      </div>
    </div>
</main>


<style>
   main {
      text-align: center;
    }
  
    .threat {
      color: red;
    }
    .safe {
      color: green;
    }
  
    .promoted {
      color: #ff9900; /* Custom color */
    }
  
    .notpromoted {
      font-style: italic;
    }
</style>