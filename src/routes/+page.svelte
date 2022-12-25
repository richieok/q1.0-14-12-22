<script>
    import {fade} from "svelte/transition"
    import Controls from "./Controls.svelte";
    let c1;
    let p1;
    let p2;
    let p3;
    let c1length;
    $:{
        if (p1){
            console.log(p1.getTotalLength());
        }
    } 
</script>

<svelte:head>
    <title>Qubit Tech</title>
</svelte:head>

<div class="outer" transition:fade>
    <div class="center">
        <svg xmlns="http://www.w3.org/2000/svg">
            <path bind:this={c1} id="circle" d="M50 150 A 100 100 0 1 1 250 150" 
                style="stroke:#fff;fill:none;stroke-width: 10;stroke-linecap:round;stroke-opacity:0.1;" 
                transform-origin="150 150"></path>
            <g>
                <path class="stripes" bind:this={p1} d="M 200 200 l 50 50"
                    style="fill:none;stroke:#fff;stroke-width:10;stroke-linecap:round;stroke-opacity:0.1"></path>
                <path class="stripes" bind:this={p2} d="M 200 200 l 50 50"
                    style="fill:none;stroke:#f33;stroke-width:10;stroke-linecap:round;stroke-opacity:0.1"
                    transform="translate(0, -20)"></path>
                <path class="stripes" bind:this={p3} d="M 200 200 l 50 50"
                    style="fill:none;stroke:#33c;stroke-width:10;stroke-linecap:round;stroke-opacity:0.1"
                    transform="translate(0, -40)"></path>
            </g>
        </svg>
        <div>
            <h2>Qubit Technologies</h2>
        </div>
    </div>
</div>

<style>
    .outer {
        position: relative;
        height: 100%;
    }
    .center {
        display: grid;
        place-items: center;
        gap: 0;
    }
    svg {
        width: 300px;
        height: 300px;
        z-index: -1;
    }
    #circle {
        animation: circle 7s linear infinite, soft-pulse 7s ease-in-out 2s infinite;
        
    }
    svg g :nth-child(1){
        animation: stripe-pulse 3s linear 1s infinite;
    }
    svg g :nth-child(2){
        animation: stripe-pulse 3s linear 2s infinite;
    }
    svg g :nth-child(3){
        animation: stripe-pulse 3s linear 3s infinite;
    }

    @keyframes circle {
        0% {
            transform: rotate(0);
        }
        50% {
            transform: rotate(180deg);
        }
        100% {
            transform: rotate(360deg);
        }
    }
    @keyframes stripe-pulse {
        0%{
            stroke-opacity: .1;
        }
        30%{
            stroke-opacity: .1;
        }
        40%{
            stroke-opacity: .5;
        }
        50%{
            stroke-opacity: .5;
        }
        60%{
            stroke-opacity: .1;
        }
        100%{
            stroke-opacity: .1;
        }
    }
    @keyframes soft-pulse {
        0%{
            stroke-opacity: .1;
        }
        50%{
            stroke-opacity: .5;
        }
        100%{
            stroke-opacity: .1;
        }
    }   
</style>