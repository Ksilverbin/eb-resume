<script lang="ts">
import ListItem from '$lib/components/ui/ListItem.svelte';
import List from '$lib/components/ui/List.svelte';
import type { Education } from '$lib/types/resume.types';

let { period, description, introduce }: Education = $props();
</script>

<div class="relative pl-6 border-l border-(--color-border-default)">
	<span class="text-sm text-(--color-text-muted) font-mono">{period}</span>
	<p class="text-(--color-text-primary) leading-relaxed text-lg mb-4">{description}</p>
	<List>
		{#each introduce as intro (intro)}
			<ListItem>
				{intro}
			</ListItem>
		{/each}
	</List>
</div>