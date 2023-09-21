<script>
    import { browser } from '$app/environment';
    import Carousel from 'svelte-carousel'
    let carousel;
    const handleNextClick = () => {
        carousel.goToNext()
    }
    const handlePrevClick = () => {
        carousel.goToPrev()
    }
</script>
{#if browser}
    <Carousel
        autoplay
        autoplayDuration={4000}
        bind:this={carousel}
    >
<div slot="prev" on:click={handlePrevClick} class="custom-arrow custom-arrow-prev">
    <i />
  </div>
        <slot />
  <div slot="next" on:click={handleNextClick} class="custom-arrow custom-arrow-next">
    <i />
  </div>
    </Carousel>
     <!-- <button on:click={handlePrevClick}>prev</button> -->
     <!-- <button on:click={handleNextClick}>Next</button> -->
{/if}
<style>
  /* custom arrows */
  .custom-arrow {
    width: 20px;
        background: var(--global-bgc);
        backdrop-filter: var(--global-bgf);
    opacity: 0.3;
    position: absolute;
    top: 0;
    bottom: 0;
    z-index: 1;
    transition: opacity 300ms ease;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    -webkit-tap-highlight-color: transparent;
  }
  .custom-arrow:hover {
    opacity: 0.5;
  }
  .custom-arrow > i {
    border: solid #1e1e1e;
    border-width: 0 5px 5px 0;
    padding: 5px;
    position: relative;
  }
  .custom-arrow-prev {
    left: 0;
  }
  .custom-arrow-prev > i {
    transform: rotate(135deg);
    right: -4px;
  }
  .custom-arrow-next {
    right: 0;
  }
  .custom-arrow-next > i {
    transform: rotate(-45deg);
    left: -4px;
  }

    </style>
