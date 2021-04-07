<script>
    import { url } from '@roxi/routify'

    const copyright_year = new Date().getFullYear();
    const navigation = [
        ['Home', './'],
        ['Profile', './profile'],
        ['Your decks', './your-decks'],
        ['Community', './community'],
        ['Archive', './archive'],
        ['Switch account', './login'],
        ['Log out', './']
    ]
</script>

<style>
    footer {
		width: 100%;
        background-color: #F5EEE6;
	}

    /* Supertext CSS */
    .supertext {
        display: flex;
        justify-content: space-evenly;
        margin-top: 25px;
    }

    .supertext h1 {
        margin: 0px;
        font-size: 1.563rem;
    }

    .supertext p {
        margin: 0px;
        color: #A59E96;
    }

    .nav-links {
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        align-items: center;

        height: 50%;
    }

    .nav-links a {
        width: 50%;
        margin: 0px;

        color: #A59E96;
        text-decoration: none;
    }

    .nav-links a:hover {
        color: #58524B;
    }

    .quick_search {
        width: 100%;

        margin-top: 10px;
        padding: 10px 15px;

        font-size: 1.125rem;
        border-width: 0px;
        border-radius: 1.25rem;
        box-shadow: 3px 3px 3px rgba(66, 66, 66, 0.2);
    }

    /* Subtext CSS */
    .subtext {
        display: flex;
        justify-content: center;
        margin: 10px 0px;
    }

    .subtext span {
        margin: 0.75rem 0rem;
    }

    .subtext p {
        margin: 0.75rem;
    }

    .subtext a {
        margin: 0.75rem;

        color: #58524B;
        text-decoration: none;
    }

    .subtext a:hover {
        opacity: 50%;
    }
</style>

<footer>
    <div class="supertext">
        <div class="column" style="width: 25%;">
            <h1> Hello there! </h1>
            <p> 
                Welcome to the Grip MTG Deckbuilder. Although there 
                are alread lots of deckbuilders around, we at Grip
                believe they all leave room for improvement. Be it
                attractive design and powerful analysis tools,
                or our deck sharing community, we feature it all.
            </p>
        </div>
        <div class="column" style="width: 20%;">
            <h1> Navigation </h1>
            <nav class="nav-links">
                {#each navigation as [name, path]}
                    <a href={$url(path)}> {name} </a>
                {/each} 
            </nav>                                               
        </div>
        <div class="column" style="width: 30%;">
            <h1> Quick search </h1>
            <input type="text" class="quick_search"/>
        </div>
    </div>
    <div class="subtext">
        <a href={$url('./privacy-policy')}> Privacy policy </a> <span>·</span>
        <a href={$url('./sitemap')}> Sitemap </a> <span>·</span>
        <a href={$url('./support')}> Support </a> <span>·</span>
        <p> © {copyright_year} Grip MTG Deckbuilder </p>
    </div>
</footer>