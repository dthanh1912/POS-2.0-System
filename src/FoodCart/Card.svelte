<script>
	import { get } from 'svelte/store';
	import { cart } from '../Stores/stores.js';
	import category_items from '../items/universal_items.js';
	import RecommendedItems from './RecommendedItems.svelte';
	export let item;
	let {
		id,
		img,
		name,
		price,
		description,
		sku,
		calo,
		serving_size,
		total_fat,
		protein,
	} = item;
	img = `img/${img}`;
	import {
		Button,
		Modal,
		ModalBody,
		ModalFooter,
		ModalHeader,
	} from 'sveltestrap';
	let open = false;
	let size = 'xl';
	var recmd_food = [];
	const toggle = () => {
		open = !open;
		inCart = get(cart)[name] ? get(cart)[name].count : 0;
	};
	var inCart = get(cart)[name] ? get(cart)[name].count : 0;

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
		inCart = get(cart)[name] ? get(cart)[name].count : 0;
		if (e.target.classList.contains('add')) {
			addToCart();
		} else {
			removeFromCart();
		}
	};
	var randomProperty = function (obj) {
		var keys = Object.keys(obj);
		return obj[keys[(keys.length * Math.random()) << 0]];
	};

	function randomFood() {
		recmd_food = [];
		var i = 0;
		var isDuplicate = false;
		for (i = 0; i < 6; i++) {
			let new_food = randomProperty(randomProperty(category_items));
			if (recmd_food.length > 0) {
				for (let i = 0; i < recmd_food.length; i++) {
					if (
						recmd_food[i].name == new_food.name ||
						new_food.name == name
					) {
						isDuplicate = true;
						break;
					}
				}
				if (!isDuplicate) {
					recmd_food.push(new_food);
				}
			} else if (new_food.name != name) {
				recmd_food.push(new_food);
			}
		}
	}

	function imgClicked() {
		toggle();
		randomFood();
	}
</script>

<div class="card">
	<img
		class="card-img-top"
		width="300"
		height="200"
		src={img}
		alt={name}
		on:click={imgClicked}
	/>
	<Modal isOpen={open} {toggle} {size} backdrop="static">
		<ModalHeader {toggle}>ADD TO CART</ModalHeader>
		<ModalBody>
			<div class="container" style="align-items: flex-start;gap: 30px;">
				<div class="left-side" style="flex-basis: 100%;">
					<h4 class="card-title">Recommended food</h4>
					<ul class="list-group">
						{#each recmd_food as item (item.id)}
							<li class="list-group-item">
								<RecommendedItems {item} />
							</li>
						{/each}
					</ul>
				</div>
				<div class="right-side" style="flex-basis: 100%;">
					<div class="header-text">
						<h5 class="card-title" style="float: left;">
							SKU: {sku}
						</h5>
					</div>
					<br />
					<br />
					<div class="header-text">
						<h4 class="card-title" style="float: left;">{name}</h4>
						<h4 class="card-title" style="float: right;">
							Price: ${price}
						</h4>
					</div>
					<div>
						<img width="100%" height="auto" src={img} alt={name} />
					</div>
					<hr />
					<div class="quantity">
						<h5 style="float: left;"><b>Quantity:</b></h5>
						<div class="button-group" style="float: right;">
							<button
								type="button"
								class="btn btn-success add"
								on:click={countButtonHandler}>+</button
							>
							{'  '}
							<span>{inCart}</span>
							{'  '}
							<Button
								class="btn btn-warning"
								color="warning"
								on:click={countButtonHandler}
								>-
							</Button>
						</div>
					</div>
					<br />
					<br />
					<hr />
					<div>
						<h5><b>Description:</b></h5>
						{description}
					</div>
					<hr />
					<div class="nutrition_info">
						<h5><b>Nutrition facts:</b></h5>
						(Amount per serving)
						<br />
						<h7><b>Serving size:</b> {serving_size}</h7>
						<br />
						<h7><b>Calories: </b>{calo}kcal</h7>
						<br />
						<h7><b>Total fat: </b>{total_fat}g</h7>
						<br />
						<h7><b>Proteins: </b>{protein}g</h7>
						<hr />
					</div>
				</div>
			</div></ModalBody
		>
		<ModalFooter>
			<Button color="primary" on:click={toggle} block>
				<object
					aria-label="shopping cart"
					type="image/svg+xml"
					data="img/svg/shopping-cart.svg"
				/>
				{' '}
				Add to cart
			</Button>
		</ModalFooter>
	</Modal>
	<div class="card-body">
		<h5 class="card-title">{name}</h5>
		<b class="card-title"> ${price}</b>
		<p class="card-title">
			{#if inCart > 0}
				<span>
					<em>({inCart} in cart)</em>
				</span>
			{:else}
				<span>
					<em>Let's add it!</em>
				</span>
			{/if}
		</p>
	</div>
	<div class="btn-group" role="group">
		<button type="button" class="btn btn-primary" on:click={addToCart}>
			<object
				aria-label="shopping cart"
				type="image/svg+xml"
				data="img/svg/shopping-cart.svg"
			/>
			Add to cart
		</button>
	</div>
</div>

<style>
	.card {
		margin: 1%;
	}

	.container {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
	}
	@media only screen and (max-width: 1000px) {
		.container {
			flex-direction: column-reverse;
			justify-content: center;
		}
		.left-side {
			margin: 10px 0px;
		}
		.list-group-item {
			width: 100%;
		}
		.list-group {
			width: 100%;
		}
		.card-title {
			float: left !important;
		}
		.card-body{
			display: flex;
			flex-direction: column;
			align-items: flex-start;
			justify-content: flex-start;
		}
	}
</style>
