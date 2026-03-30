<script lang="ts">
import ListItem from '$lib/components/ui/ListItem.svelte';
import List from '$lib/components/ui/List.svelte';
import type { Experience } from '$lib/types/resume.types';

let { company, period, role, description, introduce }: Experience = $props();

</script>

<div class="relative pl-6 border-l border-(--color-border-default)">
	<div class="flex flex-col gap-3 md:flex-row md:justify-between items-start mb-1">
		<h3 class="text-2xl font-bold order-2 md:order-1">{company}</h3>
		<span class="text-sm text-(--color-text-muted) font-mono order-1 md:order-2">{period}</span>
	</div>
	<p class="mb-3 text-(--color-text-muted)">{role}</p>
	<p class="text-(--title-sub) leading-relaxed mb-4">{description}</p>
	<List>
		{#each introduce as intro (intro)}
			<ListItem>
				{intro}
			</ListItem>
		{/each}
	</List>
</div>