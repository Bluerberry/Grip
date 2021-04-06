<script>
    import { url } from '@roxi/routify'

    const copyright_year = new Date().getFullYear();

    // Switches active element to specified id
    function set_active(id) {
        // Unset all active elements
        const menu_items = [...document.getElementsByClassName('active')];
        menu_items.forEach(
            menu_item => { menu_item.classList.remove('active'); }
        );

        // Set specified element
        if (id != null) {
            document.getElementById(id).classList.add('active');
        }
    }
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

    .nav_links {
        float: left;
        width: 50%;

        margin: 0px;
        padding: 0px;

        list-style-type: none;
    }

    .nav_links a {
        margin: 0px;

        color: #A59E96;
        text-decoration: none;
    }

    .nav_links a:hover {
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
        <nav class="column" style="width: 20%;">
            <h1> Navigation </h1>
            <ul class="nav_links">
                <li><a href={$url('./')}           on:click={ () => set_active(null) }>         Home       </a></li>
                <li><a href={$url('./profile')}    on:click={ () => set_active(null) }>         Profile    </a></li>
                <li><a href={$url('./your-decks')} on:click={ () => set_active('your-decks') }> Your decks </a></li>
                <li><a href={$url('./community')}  on:click={ () => set_active('community') }>  Community  </a></li>
            </ul>
            <ul class="nav_links">
                <li><a href={$url('./archive')}    on:click={ () => set_active('archive') }> Archive        </a></li>
                <li><a href={$url('./login')}      on:click={ () => set_active(null) }>      Switch account </a></li>
                <li><a href={$url('./')}           on:click={ () => set_active(null) }>      Log out        </a></li>
            </ul>                                                      
        </nav>
        <div class="column" style="width: 30%;">
            <h1> Quick search </h1>
            <input type="text" class="quick_search"/>
        </div>
    </div>
    <div class="subtext">
        <a href={$url('./privacy-policy')} on:click={ () => set_active(null) }> Privacy policy </a> <span>·</span>
        <a href={$url('./sitemap')}        on:click={ () => set_active(null) }> Sitemap        </a> <span>·</span>
        <a href={$url('./support')}        on:click={ () => set_active(null) }> Support        </a> <span>·</span>
        <p> © {copyright_year} Grip MTG Deckbuilder </p>
    </div>
</footer>