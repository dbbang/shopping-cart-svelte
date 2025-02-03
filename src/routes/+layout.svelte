<script lang="ts">
	import '../app.css';
</script>

<div class="flex flex-col h-screen">
	<div class="w-full h-[30px] bg-slate-700">HEADER</div>
	<slot />
	<div class="w-full h-[30px] bg-slate-700">FOOTER</div>
</div>
