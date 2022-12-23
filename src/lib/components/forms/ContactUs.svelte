<script>
    export let inputsStuff;
    
    function buildInput(node, val){
        for (let attr in val){
            console.log(attr);
            node.setAttribute( attr, val[attr] )
        }
    }
</script>

<form method="post">
    <div class="input-group">
        {#if inputsStuff}
            {#each inputsStuff as item}
                {#if item.htmltag === "input"}
                    <label for="{item.name}">{item.name}: </label>
                    <input use:buildInput={item}>
                {:else if item.htmltag === "textarea"}
                    <label for="{item.name}">{item.name}: </label>
                    <textarea use:buildInput={item}></textarea>
                {/if}
            {/each}
        {/if}
    </div>
    <div class="button-align">
        <button type="submit">Submit</button>
    </div>
</form>

<style>
    .input-group {
        display: grid;
        grid-template-columns: auto;
        border-radius: .5em;
    }
    form {
        position: relative;
        width: 300px;
        text-transform: capitalize;
        padding: .5em 1em 0;
        border-radius: 1em;
        background-color: hsl(257, 10%, 26%);
    }
    form input, textarea, button {
        padding: .5em;
        border-radius: .5em;
    }
    form input::selection, textarea::selection{
        color: white;
        background-color: black;
    }
    form label {
        padding: .5em;
    }
    .button-align {
        display: flex;
        justify-content: flex-end;
        padding: 1em 0;
    }
    button {
        border: none;
    }
</style>