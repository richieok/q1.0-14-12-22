<script>
    import ContactUs from "../../lib/components/forms/ContactUs.svelte";
    const inputsStuff = [
        { htmltag: "input", name: 'email', type: 'email', placeholder: 'abcd@efg.xyz'},
        { htmltag: "textarea", name: 'message', rows: '4'}
    ]
</script>

<svelte:head>
    <title>Contact Us</title>
</svelte:head>

<div>
    <ContactUs {inputsStuff}/>
</div>

<style>
    div {
        height: 100%;
        display: grid;
        place-items: center;
    }
</style>