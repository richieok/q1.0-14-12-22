<script>
    import {onDestroy} from "svelte"
    import {fade} from "svelte/transition"
    import {notification} from "./appstores.js"
    let timeout

    $: {
        if ($notification?.length){
            if (!timeout){
                console.log("running");
                timeout = setTimeout(()=>{
                    notification.update( n => {
                        return n = n.slice(1)
                    })
                    clearTimeout(timeout)
                    timeout = null
                }, $notification[0].timeout - Date.now())
            }
        }
    }

    onDestroy(()=>{
        clearTimeout(timeout)
    })
</script>

{#if $notification?.length}
    <div>
        {#each $notification as {msg}}
            <p transition:fade>{msg}</p>
        {/each}
    </div>
{/if}

<style>
    div {
        position: fixed;
        right: 1em;
        top: 4em;
    }
    p {
        padding: .25em .5em;
        width: 10em;
        color: black;
        background-color: white;
        border-radius: .5em;
        margin: .25em 0;
    }
</style>