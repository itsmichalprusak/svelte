<script>
	import Nested from './Nested.svelte';

	export let count;
	export let idToValue = Object.create(null);

	function ids() {
		return new Array(count)
			.fill(null)
			.map((_, i) => ({ id: 'id-' + i}))
			.reverse();
	}
</script>

<input type='number' bind:value={count}>

<ol>
	{#each ids() as object (object.id)}
		<Nested bind:value={idToValue[object.id]} id={object.id}>
			{object.id}: value is {idToValue[object.id]}
		</Nested>
	{/each}
</ol>