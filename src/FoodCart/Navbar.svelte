<script>
	import { cart } from '../Stores/stores.js';
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	let cart_sum = 0;
	let price_sum = 0;

	cart.subscribe((items) => {
		const itemValues = Object.values(items);
		cart_sum = 0;
		itemValues.forEach((item) => {
			cart_sum += item.count;
		});
	});

	let currentCategory = '';
	function goToHome() {
		currentCategory = '';
		dispatch('nav', {
			option: 'home',
		});
	}
	function goToCupcake() {
		currentCategory = 'cupcake';
		dispatch('nav', {
			option: 'cupcake',
		});
	}
	function goToDrink() {
		currentCategory = 'drink';
		dispatch('nav', {
			option: 'drink',
		});
	}
	function goToBurger() {
		currentCategory = 'burger';
		dispatch('nav', {
			option: 'burger',
		});
	}
	function goToSandwich() {
		currentCategory = 'sandwich';
		dispatch('nav', {
			option: 'sandwich',
		});
	}
	function goToCheckout() {
		currentCategory = '';
		dispatch('nav', {
			option: 'checkout',
		});
	}
	function goToAboutUs() {
		currentCategory = 'aboutUs';
		dispatch('nav', {
			option: 'aboutUs',
		});
	}
</script>

<nav
	class="navbar navbar-dark bg-primary navbar-expand-lg navbar-dark sticky-top"
>
	<div class="container">
		<a class="navbar-brand logo-font" id="brand" on:click={goToHome}>
			Fast-Food Order
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-toggle="collapse"
			data-target="#navbarNavDropdown"
			aria-controls="navbarNavDropdown"
			aria-expanded="false"
			aria-label="Toggle navigation"
		>
			<span class="navbar-toggler-icon" />
		</button>

		<div class="collapse navbar-collapse" id="navbarNavDropdown">
			<ul class="navbar-nav mr-auto">
				<li class="nav-item">
					<a
						class="nav-link"
						href={'#'}
						on:click={goToCupcake}
						class:active={currentCategory === 'cupcake'}>Cupcake</a
					>
				</li>
				<li class="nav-item">
					<a
						class="nav-link"
						href={'#'}
						on:click={goToDrink}
						class:active={currentCategory === 'drink'}>Drink</a
					>
				</li>
				<li class="nav-item">
					<a
						class="nav-link"
						href={'#'}
						on:click={goToBurger}
						class:active={currentCategory === 'burger'}>Burger</a
					>
				</li>
				<li class="nav-item">
					<a
						class="nav-link"
						href={'#'}
						on:click={goToSandwich}
						class:active={currentCategory === 'sandwich'}
						>Sandwich</a
					>
				</li>
				<li class="nav-item">
					<a
						class="nav-link"
						href={'#'}
						on:click={goToAboutUs}
						class:active={currentCategory === 'aboutUs'}>About Us</a
					>
				</li>
			</ul>
		</div>
		<ul class="navbar-nav ml-auto">
			<li class="nav-item active">
				<a class="nav-link" on:click={goToCheckout} href={'#'}
					>Items in Cart
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="24"
						height="24"
						fill="currentColor"
						class="bi bi-cart-dash-fill"
						viewBox="0 0 16 16"
					>
						<path
							d="M.5 1a.5.5 0 0 0 0 1h1.11l.401 1.607 1.498 7.985A.5.5 0 0 0 4 12h1a2 2 0 1 0 0 4 2 2 0 0 0 0-4h7a2 2 0 1 0 0 4 2 2 0 0 0 0-4h1a.5.5 0 0 0 .491-.408l1.5-8A.5.5 0 0 0 14.5 3H2.89l-.405-1.621A.5.5 0 0 0 2 1H.5zM6 14a1 1 0 1 1-2 0 1 1 0 0 1 2 0zm7 0a1 1 0 1 1-2 0 1 1 0 0 1 2 0zM6.5 7h4a.5.5 0 0 1 0 1h-4a.5.5 0 0 1 0-1z"
						/>
					</svg>
				</a>
			</li>
			<li class="nav-link active">
				{#if cart_sum > 0}
					{cart_sum}
				{/if}
			</li>
		</ul>
	</div>
</nav>

<br />

<style>
	#brand {
		cursor: pointer;
	}
</style>
