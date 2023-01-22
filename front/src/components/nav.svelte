<header>
    <h1 class="logo">VOCATIS</h1>
    <input id="nav-toggle"type="checkbox" class="nav-toggle">
    <nav>
        <ul>
            <li><a href="/verwaltung">Verwaltung</a></li>
            <li><a href="/verwaltung">Vermarktung</a></li>
            <li><a href="/verwaltung">Instandhaltung</a></li>
            <li><a href="/verwaltung">Zertifikate</a></li>
        </ul>
    </nav>
    <label for="nav-toggle" class="nav-toggle-label">
        <span></span>
    </label>
</header>

<style>

* {
    margin: 0;
    padding: 0;
}

:root {
    --background: rgba(255, 255, 255, 1);
    --mobile-background: rgba(176, 0, 86, 1);
}

header {
    background: var(--background);
    text-align: left;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 999;
    height: 70px;
    box-shadow: 0px 0.01em 0.4em black;
}

h1 {
    padding: 0.5em;
    height: 100%;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
}

.nav-toggle {
    display: none;
}

.nav-toggle-label {
    padding: 1em;
    position: absolute;
    top: 0;
    right: 0;
    height: 100%;
    display: flex;
    align-items: center;
}

.nav-toggle-label span,
.nav-toggle-label span::before,
.nav-toggle-label span::after {
    display: block;
    background: black;
    height: 2px;
    width: 2em;
    border-radius: 2px;
    position: relative;
}

.nav-toggle-label span::before,
.nav-toggle-label span::after {
    content: '';
    position: absolute;
}

.nav-toggle-label span::before {
    bottom: 7px;
}

.nav-toggle-label span::after {
    top: 7px;
}

nav {
    background: var(--background);
    position: absolute;
    text-align: left;
    top: 100%;
    left: 0;
    width: 100%;
    transform: scale(1, 0);
    transform-origin: top;
    transition: transform 100ms ease-in-out;
    /* display: none; */
}

nav ul {
    list-style: none;
}

nav li {
    padding: 2em;
    background-color: var(--mobile-background);
    margin-bottom: 0.2em;
    text-align: center;
}

nav a {
    color: white;
    text-decoration: none;
    font-size: 1.2rem;
    opacity: 0;
    transition: opacity 50ms ease-in-out;
}

.nav-toggle:checked ~ nav {
    transform: scale(1, 1);
}

.nav-toggle:checked ~ nav a {
    opacity: 1;
    transition: opacity 80ms ease-in-out 80ms;
}

@media screen and (min-width: 800px) {
    .nav-toggle-label {
        display: none;
    }

    header {
        display: grid;
        grid-template-columns: 1fr auto minmax(600px, 3fr) 1fr; 
    }

    .logo {
        grid-column: 2 / 3;
    }

    nav {
        all: unset;
        grid-column: 3 / 4;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }

    nav a {
        opacity: 1;
        color: black;
    }

    nav ul {
        display: flex;
    }

    nav li {
        margin: 0;
        padding: 0.5em;
        background-color: white;
    }
}

</style>