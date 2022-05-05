<script>
	import Menu from './FoodCart/Menu.svelte';
	import Navbar from './FoodCart/Navbar.svelte';
	import Checkout from './Checkout/Checkout.svelte';
	import categories from './items/universal_items.js';
	import HomeMenu from './FoodCart/HomeMenu.svelte';
	import AboutUs from './FoodCart/AboutUs.svelte';
	let nav = 'home';

	function navHandler(event) {
		nav = event.detail.option;
	}
</script>

<svelte:head>
	<title>KTVT POS</title>
	<html lang="en" />
</svelte:head>

<Navbar on:nav={navHandler} />
{#if nav === 'home'}
	<HomeMenu />
{:else if nav === 'checkout'}
	<Checkout />
{:else if nav === 'cupcake'}
	<Menu items={categories['cupcake']} />
{:else if nav === 'drink'}
	<Menu items={categories['drink']} />
{:else if nav === 'burger'}
	<Menu items={categories['burger']} />
{:else if nav === 'sandwich'}
	<Menu items={categories['sandwich']} />
{:else if nav === 'aboutUs'}
	<AboutUs />
{/if}
