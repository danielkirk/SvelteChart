<canvas id="canvasID" ></canvas>

<script>
    import { Chart } from 'chart.js';
    import { onMount, onUpdate } from 'svelte';
    export let 
      config
    , width
    , height
// need way to conditionally render the id of the canvas prior to mounting the chart //
// https://www.chartjs.org/docs/latest check here for config usage //
    const ctx = document.getElementById('canvasID');
// setting configuration for canvas that chart is rendered in //
    ctx.id = config.type;
    ctx.width = width;
    ctx.height = height;
// chart creation configurations //
    const createChart = new Chart(ctx, {
        type: config.type,
        data: config.data,
        options: config.options
    });
     onMount(createChart);
</script>