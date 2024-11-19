<script>
	import * as d3 from 'd3';
	import LinePlot from '../components/LinePlot.svelte';
	let data = d3.ticks(-2, 2, 200).map(Math.sin);

	function onMousemove(e) {
		const [x, y] = d3.pointer(e);
		data = data.slice(-200).concat(Math.atan2(x, y));
	}
</script>

<div onmousemove={onMousemove}>
	<LinePlot {data} />
</div>
