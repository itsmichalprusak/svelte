<script>
	export let visible;

	function foo(node, params) {
		return {
			duration: 100,
			tick: t => {
				node.foo = t;
			}
		};
	}
</script>

{#if visible}
	<span out:foo>hello</span>
{/if}