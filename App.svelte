

<script>
  import {setContext} from 'svelte'
  import Basics from "./Basics.svelte";
  import Form from "./Form.svelte";
  import Props from "./Props.svelte";
  import Reactive from "./Reactive.svelte";
  import CompC from "./components/compC.svelte";
  import Popup from './components/Popup.svelte';
  import Outer from './components/Outer.svelte';

//props
 const name='Sandhiya'  
 const channel ='codevolution'
 const obj={
	name:'barry',
	nickname:'blade',
 }

//context API
 const userName='Vishnu' 
 //Setcontext tp provide the value from the parent component
 setContext('username-context',userName) //invoke the setcontext fun //1st argument can be anything
  
 //popup
  let showPopup = false

  function closePopup(event){
	 showPopup =false
	 console.log(event.detail)   
  }

   //Forwarding events
   function handleGreet(event){
		alert(event.detail)
	 }

  </script>
  
  <main>
    
   
	<Basics/>
	<Form/>
	<Reactive/>
	<Props name='Bruce' nickname='bru'/>
	<Props name='Flora' nickname='flow'/>
	<Props name='Alphine' nickname='Alph'/>
	<Props {...obj} />  <!--... is the spread operator -->
    
	
	
	<h2 class="text-center pt-5">App Component username - {userName}</h2>
	<CompC/>
    

	<div class="text-center p-5 border-2 border-gray-400   m-5 "> 
		<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"    
		on:click={() => (showPopup=true)}>Show Popup</button> <!--on click the showpopup will be true-->
		{#if showPopup} 
		<Popup on:close={(closePopup)}/>
		{/if}
	</div>

	<Outer on:greet={handleGreet}/>
   
   
  
    
  </main>
  
  <style>
   
  </style>