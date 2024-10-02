<script lang="ts">
	import Button from '$lib/components/button.svelte';

	type Item = {
		name: string;
		price: number;
		img: string;
	};

	type CartItem = {
		count: number;
		item: Item;
	};

	let catalog: Item[] = [
		{
			name: 'Turkey',
			price: 200,
			img: 'https://www.allrecipes.com/thmb/cVQL59QQ70ikOvtpcZU3TmQRPkg=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/ALR-166160-juicy-thanksgiving-turkey-VAT-4958-4x3-e9fdc719770d4661b5d831f958e6eb78.jpg'
		},
		{
			name: 'Beef',
			price: 100,
			img: 'https://www.eatthis.com/wp-content/uploads/sites/4/2022/06/packaged-meat.jpg?quality=82&strip=1&w=640'
		},
		{
			name: 'Chicken',
			price: 300,
			img: 'https://cdn.greatlifepublishing.net/wp-content/uploads/sites/2/2020/06/01160949/chicken-video.jpg'
		}
	];

	let cart: Item[] = [];

	const addToCart = (itemToAdd: Item) => {
		cart = [...cart, itemToAdd];
	};

	const removeFromCart = (indexToRemove: number) => {
		cart = cart.filter((_, cartIndex) => {
			return cartIndex !== indexToRemove;
		});
	};
</script>

<div class="p-4 flex flex-col gap-3">
	<h1>Catalog</h1>
	<div class="flex gap-2 flex-wrap">
		{#each catalog as item}
			<div class="flex flex-col justify-between border">
				<img src={item.img} class="max-w-[200px]" alt={item.name} />
				<span>{item.name}: ${item.price}</span>
				<Button text="Add to cart" onClick={() => addToCart(item)} />
			</div>
		{/each}
	</div>

	<h1>Cart</h1>
	{#if cart.length > 0}
		<div class="flex gap-2 flex-wrap">
			{#each cart as item, index}
				<div class="flex flex-col justify-between border">
					<img src={item.img} class="max-w-[200px]" alt={item.name} />
					<span>{item.name}: ${item.price}</span>
					<Button text="Remove from cart" onClick={() => removeFromCart(index)} />
				</div>
			{/each}
		</div>
	{/if}
</div>
