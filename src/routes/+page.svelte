<script>
    import Carousel from '$comps/carousel.svelte'
    import Color from '$comps/color.svelte'
    import CardSection from '$comps/card-section.svelte'
    import Header from '$comps/header.svelte'
    import { colors } from '$lib'
</script>
<Header />
<div class="carousel">
    <Carousel>
        {#each Object.keys( colors ) as text, idx }
            <Color color={colors[text]} {text} {idx} />
        {/each}
    </Carousel>
</div>
<div class="card-section">
    <CardSection />
</div>
<style>
    .card-section {
        width: 80vw;
        margin: 32px auto 64px auto;
        /* height: 200vh; */
    }
    :global(body) {
        margin: 0;
        --global-bgc: #151934cc; 
        --global-bgf: saturate(3) blur(10px);
        background: conic-gradient(from 180deg at 0% 100%, rgb(55, 20, 77), rgb(75, 1, 103));
    }
    .carousel {
        border: 1px solid #151934cc;
        height: 600px;
    }
</style>
