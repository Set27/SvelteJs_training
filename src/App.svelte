<script lang="ts">
	import { onMount } from "svelte";
	import CreatePollForm from "./components/CreatePollForm.svelte";
	import Footer from "./components/Footer.svelte";
	import Header from "./components/Header.svelte";
	import Tabs from "./share/Tabs.svelte";

	let items = ["Current Polls", "Add New Poll"];
	let activeItem = items[0];

	const tabChange = (e) => {
		// console.log(e);
		activeItem = e.detail;
	};

	onMount(() => {
		window.addEventListener('keydown', (event) => {
			if(event.key === 'ArrowRight'){
				// console.log(event)
				activeItem = items[1]
			}
			else if(event.key === 'ArrowLeft'){
				// console.log(event)
				activeItem = items[0]
			}
		});
	});
</script>

<Header />

<main>
	<Tabs {activeItem} {items} on:tabChange={tabChange} />
	{#if activeItem === items[0]}
		<p>Current polls</p>
	{:else if activeItem === items[1]}
		<CreatePollForm />
	{/if}
</main>

<Footer />

<style>
	main {
		max-width: 1200px;
		/* text-align: center; */
		margin: 0 auto;
	}
</style>
