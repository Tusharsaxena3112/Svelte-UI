<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./components/Tabs.svelte";
	import Series from "./components/Series.svelte";
	import Movies from "./components/Movies.svelte";

	let items = ["Series","Movies"];
	let activeItem = "Series";

	const handleTabChange = (e) =>{
		activeItem = e.detail; 
	}
	
</script>

<main>
  <Header/>
  <Tabs on:tabChange={handleTabChange} {items} {activeItem}/>
  {#if activeItem === 'Series'}
  	<Series/>
	  {:else}
	  <Movies/>
  {/if}
  
  <Footer/>
</main>

<style>
	main{
		margin: auto 50px;
		background-color: blanchedalmond;
		padding:10px;
		box-shadow: 2px 2px 2px 2px white;
	}
</style>
