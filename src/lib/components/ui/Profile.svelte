<script lang="ts">
import ListItem from '$lib/components/ui/ListItem.svelte';
import List from '$lib/components/ui/List.svelte';
import Section from '$lib/components/ui/Section.svelte';
import type { Profile } from '$lib/types/resume.types';

let { name, title, contact, headline, introduce }: Profile = $props();
</script>

<Section>
	<h1 class="text-4xl font-bold">{name}</h1>
	<p class="text-xl text-(--color-text-muted) mt-2">{title}</p>
	<div class="mt-4 flex gap-4 text-sm text-(--color-text-secondary)">
		<a href="mailto:{contact.email}" class="hover:underline">Email</a>
		<a href="https://{contact.github}" target="_blank" class="hover:underline">GitHub</a>
	</div>
	<div class="border border-gray-500 p-4 rounded-lg my-6">
		{headline}
	</div>
	<List>
		{#each introduce as intro (intro)}
			<ListItem>
				{intro}
			</ListItem>
		{/each}
	</List>
</Section>