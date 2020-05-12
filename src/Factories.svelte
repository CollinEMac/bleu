<script>
    import { onMount } from 'svelte';
    export let playerCount;

    onMount(() => {
        var c = document.getElementById("factoryCanvas");
        var ctx = c.getContext("2d");

        const width = ctx.canvas.width = 0.99 * window.innerWidth;
        const height = ctx.canvas.height = 0.25 * window.innerHeight;

        const radius = 0.1 * height;
        let xValues;
        let yValues;

        // Flex number of factories based on player count
        if (playerCount == 4) {

            xValues = [
                0.3 * width - radius,
                0.6 * width - radius,
                0.9 * width - radius,
            ]

            yValues = [
                0.3 * height - radius,
                0.6 * height - radius,
                0.9 * height - radius,
            ]
        }

        // Draw the factories
        for (const y in yValues) {
            for (const x in xValues) {
                ctx.beginPath();
                ctx.arc(xValues[x], yValues[y], radius, 0, 2 * Math.PI);
                ctx.stroke();
            }
        }
    });
</script>

<canvas id="factoryCanvas"/>