<script lang="ts">

import type { Certificate } from '$lib/types/resume.types';

let { name, date, organization }: Certificate = $props();
</script>

<div class="pl-6 border-l border-(--color-border-default) flex flex-wrap items-baseline gap-1">
	<span>{name}</span>
	<span class="text-sm text-(--color-text-muted) font-mono">
		({date} {organization})
	</span>
</div>