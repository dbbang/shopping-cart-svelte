<script lang="ts">
	export let text: string = '';
	export let color: string = 'bg-slate-600';
	export let disabled: boolean = false;
	export let onClick: (() => void) | undefined = undefined;

	const handleClick = () => {
		onClick?.();
		// const audio = new Audio('/fart-meme-sound.mp3');
		// audio.play();
	};
</script>

<button class={`border border-black p-2 text-white ${color}`} {disabled} on:click={handleClick}>
	{text}
</button>
