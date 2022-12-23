<script>
    import {page} from "$app/stores"
    export let menuList
</script>

<div>
    <ul>
        {#each menuList as {href, name}}
            <li ><a class:active={$page.url.pathname === href} href={href}>{name}</a></li>
        {/each}
    </ul>
</div>

<style>
    div {
        height: 4em;
        padding: 0 1em;
    }
    ul {
        display: flex;
        height: 100%;
    }
    li {
        list-style: none;
        text-transform: capitalize;
        line-height: 4em;
        padding: 0 .1em;
    }
    a {
        text-decoration: none;
        height: 100%;
        padding: .3em;
        font-weight: bold;
        border-radius: .3em;
        transition: 1s background-color;
    }
    .active {
        background-color: white;
        color: black;
    }

    @media (min-width: 600px){
        li {
            padding: 0 .3em;
        }
    }
</style>