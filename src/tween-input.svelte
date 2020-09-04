<svelte:options tag="tween-input" />

<script>
	import { afterUpdate, beforeUpdate, onMount } from "svelte";
	import { tweened, spring } from "svelte/motion";
	import { cubicOut, linear, elasticIn, sineIn, quintIn } from "svelte/easing";

	export let value = 0;

	beforeUpdate(() => {
		let val = document.createElement("div");
		val.textContent = value == undefined ? "value is undefined (beforeUpdate)" : "value is " + value  + " (beforeUpdate)";
		document.body.appendChild(val);
	});
	afterUpdate(() => {
		let val = document.createElement("div");
		val.textContent = value == undefined ? "value is undefined (afterUpdate)" : "value is " + value  + " (beforeUpdate)";
		document.body.appendChild(val);
	});
	onMount(() => {	
		let val = document.createElement("div");
		val.textContent = value == undefined ? "value is undefined (onMount)" : "value is " + value  + " (beforeUpdate)";
		document.body.appendChild(val);
	});
</script>

<main>
	<p>{value}</p>
</main>