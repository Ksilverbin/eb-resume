<script lang="ts">
let { children } = $props();
</script>

<li class="relative pl-5 before:absolute before:left-0 before:top-[0.6em] before:h-1.5 before:w-1.5 before:rounded-full before:bg-(--title)">
	{#if children}
		{@render children()}
	{/if}
</li>