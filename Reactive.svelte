<script>
  //method 1
  let firstName = "Mark";
  let lastName = "Antony";

  //method 2 - Reactive Declaration
  $: fullName = `${firstName} ${lastName}`;

  // REACTIVE STATEMENT
  $: {
    const greet = `Fullname is ${firstName} ${lastName}`;
    console.log(greet);
  }

  //method 1
  let items = [
    { id: 1, title: "TV", price: 100 },
    { id: 1, title: "Phone", price: 1000 },
    { id: 1, title: "Laptop", price: 5000 },
  ];

  //method 2 - Reactive Declaration
  $: total = items.reduce((total, curr) => (total = total + curr.price), 0);


  let volume =0;
  $: if (volume < 0) {
    alert(`cant go lower`);
    volume = 0;
  } else if (volume > 20) alert(`cant go higher`);
  volume = 20;
</script>

<main class="p-5 text-center">

    <h2 class="text-lg">Current Volume {volume}</h2>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4" on:click={() => (volume += 2)}>Increase Volume</button>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4" on:click={() => (volume -= 2)}>Decrease Volume</button>
   
  <div class="py-5">
    <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
    on:click={() => {
      firstName = "mia";
      lastName = "dean";
    }}
  >
    change me
  </button>
  </div>
 

  <h1 class="text-2xl mt-4">How are you {firstName}?</h1>
  <h2 class="text-lg">{fullName}</h2>

  
  <h2 class="text-lg mt-4">
    <!-- 0 - is the initial total -->
    Total - {items.reduce((total, curr) => (total = total + curr.price), 0)}
  </h2>

  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4"
    on:click={() => (items = [...items, { id: 4, title: "AC", price: 9000 }])}
  >
    Add here
  </button>

  <h2 class="text-lg mt-4">
    Total - ${total}
  </h2>
</main>

<style>
</style>
