<script>
    import {data} from '$lib'
    // export let layout
    import Card from '$comps/card.svelte'
    import { PackingGrid, FrameGrid, JustifiedGrid } from "@egjs/svelte-grid";
    const layout = 'pack'
    const gap = 5;
    const defaultDirection = "end";

    const busyFrame = [
        [1, 1, 2, 3],
        [1, 1, 4, 5],
        [6, 7, 8, 8],
        [9, 9, 10, 11],
        [12, 13, 14, 15],
        [16, 16, 17, 17],
        [18, 18, 17, 17],
        [18, 18, 19, 20]
    ];
    const simpleFrame = [
        [1, 2, 3, 4]
    ]
    const altFrame = [
        [1, 2, 3, 4],
        [5, 6, 7, 7],
        [8, 9, 10, 11],
        [12, 12, 13, 14]
    ]
    const rectSize = 0;
    const useFrameFill = true;
</script>
<h2>Section Header</h2>
<FrameGrid
    class="container"
    {defaultDirection}
    {gap}
    frame={simpleFrame}
    {rectSize}
    {useFrameFill}
>
>
        {#each data.slice(0,8) as datum, idx}
    <Card {datum} height={ ( ( idx % 5  ) * 100 ) + 100 } />
{/each}
        </FrameGrid>
        <h2>Section Header</h2>
        <FrameGrid
        class="container"
    {defaultDirection}
    {gap}
    frame={altFrame}
{rectSize}
    {useFrameFill}
    >
>
{#each data.slice(9,23) as datum, idx}
    <Card {datum} height={ ( ( idx % 5  ) * 100 ) + 100 } />
        {/each}
</FrameGrid>



        <h2>Section Header</h2>
        <FrameGrid
        class="container"
    {defaultDirection}
    {gap}
    frame={busyFrame}
{rectSize}
    {useFrameFill}
    >
>
{#each data as datum, idx}
    <Card {datum} height={ ( ( idx % 5  ) * 100 ) + 100 } />
        {/each}
</FrameGrid>
<style>

</style>
