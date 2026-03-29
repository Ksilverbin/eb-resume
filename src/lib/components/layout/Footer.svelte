<script lang="ts">

import { formatDate } from '$lib/utils/date-formatter';

let updatedAt = formatDate(new Date());

</script>

<footer class="border-t border-[#4b4b4d] pt-4 pb-10">
	<div class="flex justify-end px-6 md:px-0 md:max-w-4xl md:mx-auto">
		<span class="text-(--description) text-sm">마지막 업데이트 일시 : {updatedAt}</span>
	</div>
</footer>