<script lang="ts">
	export let text: string = '';
	export let onClick: (() => void ) | undefined = undefined;
</script>

<button class="border border-black p-2 bg-slate-600 text-white" on:click={onClick}>
	{text}
</button>
