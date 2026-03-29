<script lang="ts">
import type { Snippet } from 'svelte';

interface Props {
	title?: string;    // '?'를 붙여서 Optional로 설정
	children?: Snippet; // Snippet 타입으로 children 정의
}

let { children, title }: Props = $props();
</script>

<section class="border-b border-(--border-dark) pb-10 mb-12 last:border-b-0 last:pb-0 last:mb-0">
	{#if title}
		<h2 class="text-4xl font-semibold mb-10">{title}</h2>
	{/if}
	{#if children}
		{@render children()}
	{/if}
</section>