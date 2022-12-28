<script lang="ts">
	import Accordion from "$lib/accordion/Accordion.svelte"
	import AccordionItem from "$lib/accordion/AccordionItem.svelte"
</script>

<h1>Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<h2>Accordion</h2>
<Accordion customClass="AccordionRoot" type="single" defaultValue="item-1" collapsible>
	<AccordionItem rootClass="AccordionItem" value="item-1">
		<span slot="trigger">Is it accessible?</span>
		<div slot="content">Yes. It adheres to the WAI-ARIA design pattern.</div>
	</AccordionItem>

	<AccordionItem rootClass="AccordionItem" value="item-2">
		<span slot="trigger">Is it unstyled?</span>
		<div slot="content">
			Yes. It's unstyled by default, giving you freedom over the look and feel.
		</div>
	</AccordionItem>

	<AccordionItem rootClass="AccordionItem" value="item-3">
		<span slot="trigger">Can it be animated?</span>
		<div slot="content">
			<div class="AccordionContentText">
				Yes! You can animate the Accordion with CSS or JavaScript.
			</div>
		</div>
	</AccordionItem>
</Accordion>
