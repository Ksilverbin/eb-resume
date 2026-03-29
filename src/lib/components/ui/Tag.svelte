<script lang="ts">
let { children } = $props();
</script>

<span class="px-2 py-1 text-xs font-medium border border-(--border) rounded">
	{#if children}
		{@render children()}
	{/if}
</span>