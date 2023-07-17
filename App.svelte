<script>
  import {setContext} from 'svelte'
  import Basics from "./Basics.svelte";
  import Form from "./Form.svelte";
  import Props from "./Props.svelte";
  import Reactive from "./Reactive.svelte";
  import CompC from "./components/compC.svelte";
  import Popup from './components/Popup.svelte';
  import Outer from './components/Outer.svelte';
  import Button from './components/Button.svelte';
  import Card from './components/Card.svelte';
  import NameLists from './components/NameLists.svelte';
  import ChildStyle from './components/ChildStyle.svelte';
  import AutoFocus from './components/AutoFocus.svelte';

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
 setContext('username-context',userName) //invoke the setcontext fun //1st argument can be anything, it is called context key
  
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
	<!-- forwarding click event -->
	<Button on:click={() =>alert(`clicked`)}>Click</Button>
   
   
   <Card>Card Content</Card> 
   <Card><h2>Card Content</h2></Card>
   <Card><img src='https://w.forfun.com/fetch/8c/8c1bda3637d8f634298ad500ae760cbb.jpeg' alt/></Card>
   <Card/> <!--card component will be displayed thru slot-->


   <!-- Named Slots -->
    <Card><div slot='header'>
		<h3>Nature:</h3>
	</div>
    </Card>
	<Card><div slot='content'>
		<img src='https://www.dreamstime.com/stock-image-beautiful-rain-forest-ang-ka-nature-trail-doi-inthanon-national-park-thailand-image36703721' alt/>
	</div>
    </Card>
	<Card><div slot='footer'>
		<h3>Check the details</h3>
	</div>
    </Card>



     <!-- slot props- the way we display the date in parent component -->
	<NameLists>
		<h3 slot='hero'  let:firstName let:lastName> <!--let directive is used to get the props-->
			{firstName} {lastName}
		</h3>  
	</NameLists>
	<NameLists>
		<h3 slot='hero'  let:firstName let:lastName>
			 {lastName} {firstName}
		</h3>  
	</NameLists>
   


	<h3>App Component global styles</h3>
    <h4>App component</h4>
	<ChildStyle/>



	<AutoFocus/>

  </main>
  
  <style>

   :global(h3){
	color: olive;
   }

	h4{
		color: chocolate;
	}
   
  </style>