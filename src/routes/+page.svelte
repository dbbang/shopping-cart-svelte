<script lang="ts">
	import Button from '$lib/components/button.svelte';

	let catalog = [
		{ name: 'Turkey', price: 200, img: '' },
		{ name: 'Beef', price: 100, img: '' },
		{ name: 'Chicken', price: 300, img: '' }
	];

  let cart = []

	// let x = 0;
	// let isOpen = false;

	// const test = (someArg?: number) => {
	// 	console.log(someArg);
	// };

	// const handleIncrease = () => {
	// 	x += 1;
	// };

	// const handleDecrease = () => {
	// 	x -= 1;
	// };

	// const handleZero = () => {
	// 	x = 0;
	// };

	// const handleOpen = () => {
	// 	isOpen = !isOpen;
	// };
</script>

<div class="p-4 flex flex-col gap-2">
	<!-- My number is {x}
	<Button text={isOpen ? 'Close' : 'Open'} onClick={handleOpen} />
	{#if isOpen}
		<div class="flex gap-2">
			<Button text="DECREASE" onClick={handleDecrease} />
			<Button text="0" onClick={handleZero} />
			<Button text="INCREASE" onClick={handleIncrease} />
		</div>
	{/if} -->

	{#each catalog as item}
		<div>{item.name}: ${item.price}</div>
	{/each}
</div>
