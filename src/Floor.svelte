<script>
    import { onMount } from 'svelte';

    onMount(() => {
        var c = document.getElementById("floorCanvas");
        var ctx = c.getContext("2d");

        const width = ctx.canvas.width = 0.99 * window.innerWidth;
        const height = ctx.canvas.height = 0.1 * window.innerHeight;
    });
</script>

<table>
    <tr>
        <td>
            <canvas id="floorCanvas"></canvas>
        </td>
    </tr>
</table>
