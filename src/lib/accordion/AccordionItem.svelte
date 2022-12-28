<script lang="ts">
	import type { Writable } from "svelte/store"
	import { getContext } from "svelte"

	export let rootClass = ""
	export let headerClass = ""
	export let triggerClass = ""
	export let contentClass = ""
	export let value = ""

	const { values, toggleValue } = getContext<{
		toggleValue(value: string): void
		values: Writable<{ [key: string]: boolean }>
	}>("values")
</script>

<div class={rootClass}>
	<h3 class={headerClass}>
		<button
			type="button"
			aria-expanded="true"
			class={triggerClass}
			aria-controls="sect1"
			id="accordion1id"
			on:click={() => toggleValue(value)}
		>
			<span class="accordion-title">
				<slot name="trigger" /> <span class="accordion-icon" />
			</span>
			{$values[value]}
		</button>
	</h3>

	<div class={contentClass} style="display: {$values[value] ? '' : 'none'};">
		<slot name="content" />
	</div>
</div>
