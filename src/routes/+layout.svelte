<script>
    import "../app.css";
    import Nav from "$lib/components/Nav.svelte";
    import Notification from "$lib/components/Notification.svelte";

    let menuList = [
        { name: "home", href: "/" },
        { name: "contact", href: "/contact" },
    ];
</script>

<main>
    <Nav {menuList} />
    <div>
        <Notification/>
        <slot />
    </div>
</main>

<style>
    main {
        height: 100vh;
    }
    div {
        height: calc(100% - 4em);
        position: relative;
    }
</style>
