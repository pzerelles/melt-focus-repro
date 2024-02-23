<script lang="ts">
	import { createDialog } from '@melt-ui/svelte';
	const {
		elements: { trigger, portalled, overlay, content, title, description, close },
		states: { open }
	} = createDialog({ openFocus: null });
</script>

<button {...$trigger} use:trigger> Open Dialog </button>

<div {...$portalled} use:portalled>
	{#if $open}
		<div {...$overlay} use:overlay />
		<div {...$content} use:content>
			<h2 {...$title} use:title>Dialog Title</h2>
			<p {...$description} use:description>Dialog description</p>
			<input type="text" name="user" />
			<button {...$close} use:close> Close Dialog </button>
		</div>
	{/if}
</div>
