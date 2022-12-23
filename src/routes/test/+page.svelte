<script>
    import {notification} from "$lib/components/appstores.js"

    const click = ()=>{
        notification.update(n => {
            return n = [...n, {msg: 'Turn off inverter', timeout: Date.now() + 4000}]
        })
    }
</script>

<svelte:head>
    <title>Test Stores</title>
</svelte:head>

<div>
    <button on:click={click}>test</button>
</div>

<style>
    div {
        position: relative;
        height: 100%;
        display: grid;
        place-items: center;
    }
    button {
        text-transform: capitalize;
        padding: .5em;
        border-radius: .5em;
    }
</style>