<script>
    import Title from '$lib/Title.svelte'
    import '../global.css'
</script>

<header>
    <Title />
    <div class="links">
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/guides">Guides</a>
    </div>
</header>
<main>
    <slot></slot>
    <div class="links">
        <a class="nav" href="/guides">View Guides</a>
        <a class="nav" href="/about">About Us</a>
    </div>
</main>
<footer>
    <p>Copyright 2022 Henkelwitz Webz</p>
</footer>
<style>
    header {
        padding: 20px 0;
        background: rgba(0,0,0,0.1);
    }
    .links {
        display: flex;
        justify-content: center;
        margin-top: 20px;
    }
    .links a {
        margin-left: 10px;
        font-size: 1.5em;
    }
    footer {
        text-align: center;
        color: gray;
    }
    main {
        display: block;
        margin: 20px auto;
        max-width: 75%;
    }
    .nav {
        background: purple;
        color: white;
        border: 1px solid white;
        border-radius: 5px;
        padding: 5px 10px;
        text-decoration: none;
        margin: 2em 1em;
    }
    .nav:hover {
        background: none;
        color: purple;
        border: 1px solid purple;
    }
</style>