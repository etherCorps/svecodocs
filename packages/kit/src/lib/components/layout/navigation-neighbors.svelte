<script lang="ts">
    import type { NavigationNeighbors } from "$lib/types.js";
    import { Button } from "$lib/components/ui/button/index.js";

    type Props = {
		navigationNeighbors: NavigationNeighbors;
    };

    let { navigationNeighbors }: Props = $props();
</script>

{#if navigationNeighbors}
	<div class="flex flex-col lg:flex-row w-full mt-6 gap-2">
		{#if navigationNeighbors?.previous}
			<Button variant="subtle"
					href={navigationNeighbors.previous.href}
					class="flex flex-col gap-2 items-start w-full h-fit p-4 text-sm rounded-lg"
			>
				<div class="inline-flex items-center gap-1.5 font-medium">
					<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide -mx-1 size-4 shrink-0 rtl:rotate-180"><path d="m15 18-6-6 6-6"></path></svg>
					<p>{navigationNeighbors.previous.title}</p>
				</div>
				<p class="text-muted-foreground truncate w-[90%] font-normal">{navigationNeighbors.previous.description}</p>
			</Button>
		{/if}
		{#if navigationNeighbors?.next}
			<Button variant="subtle"
				href={navigationNeighbors.next.href}
				class="flex flex-col gap-2 items-end w-full h-fit p-4 rounded-lg text-end text-sm"
			>
				<div class="inline-flex items-center gap-1.5 font-medium flex-row-reverse">
					<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide -mx-1 size-4 shrink-0 rtl:rotate-180"><path d="m9 18 6-6-6-6"></path></svg>
					<p>{navigationNeighbors.next.title}</p>
				</div>
				<p class="text-muted-foreground truncate w-[90%] font-normal">{navigationNeighbors.next.description}</p>
			</Button>
		{/if}
	</div>
{/if}