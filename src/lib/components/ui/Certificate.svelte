<script lang="ts">

import type { Certificate } from '$lib/types/resume.types';

let { name, date, organization }: Certificate = $props();
</script>

<div class="relative pl-6 border-l border-(--border)">
	<span>{name}</span>
	<span class="text-sm text-(--description) font-mono">
		({date} {organization})
	</span>
</div>