<script lang="ts">
let { children } = $props();
</script>

<ul class="flex flex-col gap-2">
	{#if children}
		{@render children()}
	{/if}
</ul>