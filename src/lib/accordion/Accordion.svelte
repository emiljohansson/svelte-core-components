<script lang="ts">
	import { setContext } from "svelte"
	import { writable } from "svelte/store"

	export let customClass = ""
	export let type: "single" | "multiple" = "multiple"
	export let defaultValue = ""
	export let collapsible = false

	const values = writable({
		[defaultValue]: true,
	})

	setContext("values", {
		values,
		toggleValue(value: string) {
			console.log("toggle", value, $values[value], collapsible && $values[value], type)
			if (type === "single") {
				if (collapsible && $values[value]) {
					console.log("here")
					$values = {}
					return
				}
				$values = {
					[value]: true,
				}
				return
			}
			$values[value] = !$values[value]
		},
	})
</script>

<div class={customClass}>
	<slot />
</div>
