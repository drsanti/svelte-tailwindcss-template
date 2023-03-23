<script>
	import { page } from "$app/stores";
	import { onMount } from "svelte";


    // onMount(() => {
    //     console.log(window.location)  
    // });


    // $: console.log($page);

    // $:{
    //     let routeId = $page.route.id;
    //     console.log(routeId);
    // }

    $: routeId = $page.route.id;


    const navs = [
        {
            title: "Home",
            href: "/"
        },
        {
            title: "About",
            href: "/about"
        },
        {
            title: "Services",
            href: "/services"
        },
        {
            title: "Contact",
            href: "/contact"
        },
    ];


</script>

<nav>
    <h1>TERNION</h1>
    <ul>
        <!-- <li>
            <a href="/" class:active={routeId=='/'}>Home</a>
        </li>
        <li>
            <a href="/about" class:active={routeId=='/about'}>About</a>
        </li>
        <li>
            <a href="/services" class:active={routeId=='/services'}>Services</a>
        </li>
        <li>
            <a href="contact" class:active={routeId=='/contact'}>Contact</a>
        </li> -->

        {#each navs as {title, href} }
            <li>
                <a {href} class:active={routeId==href} {title} >{title}</a>
            </li>
        {/each}

    </ul>
</nav>

<style>
    nav {
        padding-left: 20px;
        padding-right: 10px;
        display: flex;
        background-color: #212529; 
    }
    ul {
        display: flex;
        margin: 0;
        margin-left: auto;
        list-style: none;
    }

    li {
        margin-top: 12px;
        margin-right: 20px;
    }

    h1 {
        margin: 0;
        font-size: 2em;
        font-weight: normal;
        color: wheat;
    }

    a{
        text-decoration: none;
        color: wheat;
    }
    .active {
        color: white;
    }

</style>

