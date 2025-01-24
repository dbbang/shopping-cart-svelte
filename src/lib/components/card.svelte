<script lang="ts">
	import Button from '$lib/components/button.svelte';

	export let onButtonClick: (() => void) | undefined = undefined;
	export let imageSrc: string;
	export let name: string;
	export let price: number;
	export let color: string;
	export let buttonText: string;
	export let count: number | undefined = undefined;
</script>

<div class="flex relative flex-col border border-gray-900 p-2 rounded-md">
	{#if count}
		<div
			class="absolute right-[-12px] top-[-13px] py-1 px-2 border border-gray-900 rounded-full bg-blue-800 text-white text-xs font-semibold"
		>
			{count}
		</div>
	{/if}
	<img src={imageSrc} class="max-w-[200px] h-full border border-gray-400" alt={name} />
	<div class="flex justify-between items-end grow p-2">
		<span>{name}:</span>
		<span>${price}</span>
	</div>
	<Button text={buttonText} {color} onClick={onButtonClick} />
</div>
