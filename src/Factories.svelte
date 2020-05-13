<script>
    import { onMount } from 'svelte';
    export let playerCount;

    const width = 0.99 * window.innerWidth;
    const height = 0.25 * window.innerHeight;

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

    let factories = []

    // Draw the factories
    for (const y in yValues) {
        for (const x in xValues) {
            factories.push({x: xValues[x], y: yValues[y]});
            factories.push({x: xValues[x] + 50, y: yValues[y]});
            factories.push({x: xValues[x] + 100, y: yValues[y]});
            factories.push({x: xValues[x] + 150, y: yValues[y]});
        }
    }

    onMount(() => {
        var c = document.getElementById("factoryCanvas");
        var ctx = c.getContext("2d");

        ctx.canvas.width = width;
        ctx.canvas.height = height;

        // Draw the factories
        // TODO: Update this so we don't do the same double loop twice in the code.
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
{#each factories as factory}
    <button style="left: {factory.x}px; top: {factory.y}px;">{factory.x}</button>
{/each}
