<script>
    import { onMount } from 'svelte';

    onMount(() => {
        var c = document.getElementById("leftBoardCanvas");
        var ctx = c.getContext("2d");

        const width = ctx.canvas.width = 0.49 * window.innerWidth;
        const height = ctx.canvas.height = 0.25 * window.innerHeight;
    });
</script>

<table>
    <tr>
        <td>
            <canvas id="leftBoardCanvas"></canvas>
        </td>
    </tr>
</table>
