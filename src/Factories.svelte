<script>
    import { onMount } from 'svelte';
    export let playerCount;

    onMount(() => {
        var c = document.getElementById("factoryCanvas");
        var ctx = c.getContext("2d");

        const width = ctx.canvas.width = 0.99 * window.innerWidth;
        const height = ctx.canvas.height = 0.25 * window.innerHeight;

        const rectangleWidth = 0.8 * height;
        const rectangleHeight = 0.2 * height;

        let xValues;
        let yValues;

        // Flex number of factories based on player count
        if (playerCount == 4) {

            xValues = [
                0.3 * width - rectangleWidth,
                0.6 * width - 2*rectangleWidth,
                0.9 * width - 3*rectangleWidth,
            ]

            yValues = [
                0.3 * height - rectangleHeight,
                0.6 * height - rectangleHeight,
                0.9 * height - rectangleHeight,
            ]
        }

        // Draw the factories
        for (const y in yValues) {
            for (const x in xValues) {
                ctx.beginPath();
                ctx.rect(xValues[x], yValues[y], rectangleWidth, rectangleHeight)
                ctx.stroke();
            }
        }
    });
</script>

<canvas id="factoryCanvas"/>