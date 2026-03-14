<script lang="ts">
	let { children } = $props();
</script>

<div class="bg-white text-jhc-dark">
	<main class="flex flex-col h-auto">
		{@render children()}
	</main>
</div>
