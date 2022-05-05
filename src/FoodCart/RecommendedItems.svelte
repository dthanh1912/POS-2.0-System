<script>
	import { get } from 'svelte/store';

	import { cart } from '../Stores/stores.js';
	export let item;
	let { name, price, img } = item;
	const cartItems = get(cart);
	var inCart = cartItems[name] ? cartItems[name].count : 0;

	function addToCart() {
		inCart++;
		cart.update((n) => {
			return {
				...n,
				[name]: {
					...item,
					count: inCart,
				},
			};
		});
	}

	function removeFromCart() {
		if (inCart > 0) {
			inCart--;
			cart.update((n) => {
				return {
					...n,
					[name]: {
						...item,
						count: inCart,
					},
				};
			});
		}
	}
	const countButtonHandler = (e) => {
		if (e.target.classList.contains('add')) {
			addToCart();
		} else {
			removeFromCart();
		}
	};
</script>

<div class="container">
	<div class="item-container">
		<img src={`img/${img}`} alt={name} class="img-container" />
		<div class="textarea">
			<h6>{name}</h6>
			<h7>Price: ${price}</h7>
		</div>
	</div>
	<div class="button-group">
		<button
			type="button"
			class="btn btn-success add"
			on:click={countButtonHandler}>+</button
		>
		{'  '}
		<span>{inCart}</span>
		{'  '}
		<button
			class="btn btn-warning"
			color="warning"
			on:click={countButtonHandler}
			>-
		</button>
	</div>
</div>

<style>
	.item-container {
		display: flex;
		gap: 20px;
		justify-content: flex-start;
		align-items: center;
		flex-grow: 3;
	}
	.container {
		display: flex;
		justify-content: flex-start;
		align-items: center;
		gap: 20px;
	}
	.img-container {
		width: 30%;
		height: 80px;
	}
	.button-group {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		flex-wrap: nowrap;
		gap: 5px;
	}

	@media only screen and (max-width: 1000px) {
		.item-container {
			gap: 10px;
		}
		.container {
			padding: 0px;
			gap: 10px;
		}
		.img-container {
			width: 30%;
			height: 50px;
		}
	}
</style>
