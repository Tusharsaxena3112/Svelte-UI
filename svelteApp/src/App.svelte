<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./components/Tabs.svelte";

	let items = ["Series","Movies"];
	let activeItem = "Series";

	const handleTabChange = (e) =>{
		activeItem = e.detail; 
	}
	
</script>

<main>
  <Header/>
  <Tabs on:tabChange={handleTabChange} {items} {activeItem}/>
  
  <Footer/>
</main>

<style>
	main{
		margin: auto 50px;
		background-color: blanchedalmond;
		padding:10px;
		box-shadow: 1px 1px 1px 1px grey;
	}
</style>
