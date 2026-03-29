<script lang="ts">
import ListItem from '$lib/components/ui/ListItem.svelte';
import Tag from '$lib/components/ui/Tag.svelte';
import List from '$lib/components/ui/List.svelte';
import type { Project } from '$lib/types/resume.types';

let { title, company, period, description, tags, introduce }: Project = $props();

</script>

<div class="relative pl-6 border-l border-(--border)">
	<div class="flex flex-col gap-3 md:flex-row md:justify-between items-start mb-1">
		<h3 class="text-2xl font-bold order-2 md:order-1">
			{title}
			<small class="text-(--description) text-sm font-normal">{company}</small>
		</h3>
		<span class="text-sm text-(--description) font-mono order-1 md:order-2">{period}</span>
	</div>
	<p class="leading-relaxed mb-4">{description}</p>
	<div class="flex flex-wrap gap-2 mb-4">
		{#each tags as tag (tag)}
			<Tag>{tag}</Tag>
		{/each}
	</div>
	<List>
		{#each introduce as intro (intro.id)}
			<ListItem>
				<div class="flex flex-col gap-1">
					<strong>{intro.subTitle}</strong>
					<span class="">
						: {intro.description}
					</span>
				</div>
			</ListItem>
		{/each}
	</List>
</div>