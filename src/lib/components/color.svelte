<script>
    export let color, text, idx
    const alpha = 1
    export const quotes=[
        "Like most others, I was a seeker, a mover, a malcontent, and at times a stupid hell-raiser.",
        "I was never idle long enough to do much thinking, but I felt somehow that some of us were making real progress, that we had taken an honest road, and that the best of us would inevitably make it over the top.",
        "At the same time, I shared a dark suspicion that the life we were leading was a lost cause, that we were all actors, kidding ourselves along on a senseless odyssey.",
        "It was the tension between these two poles - a restless idealism on one hand and a sense of impending doom on the other - that kept me going.",
        "It gave me a strange feeling, and the rest of that night I didn’t say much, but merely sat there and drank, trying to decide if I was getting older and wiser, or just plain old.",
        "I felt a tremendous distance between myself and everything real.",
        "No matter how much I wanted all those things that I needed money to buy, there was some devilish current pushing me off in another direction -- toward anarchy and poverty and craziness. That maddening delusion that a man can lead a decent life without hiring himself out as a Judas Goat.",
        "sounds of life and movement, people getting ready and people giving up, the sound of hope and the sound of hanging on, and behind them all, the quiet, deadly ticking of a thousand hungry clocks",
        "What got me by during that time was conceiving of the history of philsophy as a kind of ass-fuck, or, what amounts to the same thing, an immaculate conception.  I imagined myself approaching an author from keyind and giving him a child that would indeed be his but would nevertheless be monstrous."
    ]
</script>
<div class="color-wrap">
    {#each color as c}
        <div class="stripe" style="background-color: rgba({ c.rgb },{alpha});" />
    {/each} 
    <a  href="/" class="wedgie">
        <p><span class="caption">{quotes[idx]}</span><span class="swap">its the {text} flag</span></p>
    </a>
</div>


<style>
    .color-wrap {
        display: flex;
        /* flex-direction: column; */
        justify-content: stretch;
        align-items: stretch;
        position: relative;
        margin: 0;
        padding: 0;
        min-height: 600px;
    }
    .stripe {
        flex: 1;
    }
    .wedgie {
        text-decoration: none;
        color:  #18b6f6;
        position: absolute; 
        bottom: 0;
        right: 0;
        /* lefT: 0; */
        width: max(600px, 44vw);
        height: 40%;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        background-color: #151934cc; 
        backdrop-filter: saturate(3) blur(10px);
        clip-path: polygon(30% 0, 100% 0, 100% 100%, 0% 100%);
        /* background: linear-gradient(152deg, rgba(2,0,36,0) 0%, rgba(9,18,127,0) 50%, rgba(21,25,52,1) 50%, rgba(21,25,52,1) 100%); */
        margin: 0;

    }
    .wedgie p {
        color: inherit;
        position: relative;
        width: 70%;
        /* width: max(600px, 44vw); */
        display: flex;
        justify-content: center;
        align-items: center;

    }
    .caption, .swap {
        padding: 16px;
        font-size: 20px;
        justify-content: stretch;
        align-items: stretch;
        transition: 300ms;
    }
    .caption {
        /* position: absolute; */
        /* left: 0; */
        display: flex;
        filter: blur(1px);
    }
    .wedgie:hover .caption {
        filter: blur(20px);
    }
    .swap {
        position: absolute;
        left: 0;
        filter: blur(20px);
    }
    .wedgie:hover .swap {
        filter: blur(1px);
    }
    </style>
