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
    /* --------- Header CSS --------- */
	header {
		position: fixed;
        top: 0px;
        z-index: 1;

        width: 100%;
        padding-right: 15px;
        background-color: #2A0C4E;
	}

    .title {
        float: left;

        margin: 0px;
        padding: 1.25rem 1.875rem;

        color: white;
        font-size: 2.188rem;
        text-align: center;
        text-decoration: none;
    }

    .menu_item {
        float: right;

        margin: 0px;
        padding: 1.875rem 0.9375rem;

        color: white;
        font-size: 1.125rem;
        text-align: center;
        text-decoration: none;

        transition: box-shadow 0.1s;
        transition-timing-function: ease-out;
        box-shadow: inset 0px 0px 0px 0px #FFF8F0;
    }

    .menu_item:hover {
        transition: box-shadow 0.1s;
        transition-timing-function: ease-out;
        box-shadow: inset 0px -8px 0px 0px #FFF8F0;
    }

    :global(.active) {
        box-shadow: inset 0px -8px 0px 0px #FFF8F0 !important;
    }

    /* Dropdown CSS */
    .dropdown {
        float: right;
        overflow: hidden;
    }

    .dropdown p {
        margin: 0;
        padding: 1.875rem 0.9375rem;

        font-size: 1.125rem;  
        color: #FFF8F0;
    }

    .dropdown-content {
        display: none;
        position: absolute;

        min-width: 10rem;
        background-color: #F5EEE6;
        box-shadow: 0px 0px 15px 3px rgba(66,66,66,.2);
        z-index: 1;
    }

    .dropdown-content a {
        display: block;
        float: none;
        padding: 0.75rem 1rem;

        color: black;
        text-align: left;
        text-decoration: none;
    }

    .dropdown-content a:hover {
        background-color: #CDC6BE;
    }

    .dropdown-content .divider {
        margin: 0px auto;
        width: 90%;
        height: 1px;

        background-color: #A59E96;
    }
    
    .dropdown:hover .dropdown-content {
        display: block;
    }
    
    /* --------- Content CSS --------- */
	.content {
        flex: 1;
        margin-top: 5.063rem;
		background-color: #FFF8F0;
	}
	
    /* --------- Footer CSS --------- */
	footer {
		width: 100%;
        background-color: #F5EEE6;
	}

    footer a:hover {
        opacity: 50%;
    }

    /* Supertext CSS */
    .supertext {
        display: flex;
        justify-content: space-evenly;
        margin-top: 25px;
    }

    .supertext h1 {
        margin: 0px;

        color: #2A0C4E;
        font-size: 1.563rem;
    }

    .supertext p {
        margin: 0px;

        color: #A59E96;
        text-align: justify;
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
        text-decoration: underline;
    }

    .quick_search {
        width: 100%;

        margin-top: 10px;
        padding: 10px 15px;

        color: black;
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

        color: black;
        text-decoration: none;
    }
</style>

<header>
    <nav>
        <a href={$url('./')}           class="title"     id="title"      on:click={ () => set_active(null) }> Grip </a>
        <a href={$url('./archive')}    class="menu_item" id="archive"    on:click={ () => set_active('archive') }> Archive </a>
        <a href={$url('./community')}  class="menu_item" id="community"  on:click={ () => set_active('community') }> Community </a>
        <a href={$url('./your-decks')} class="menu_item" id="your-decks" on:click={ () => set_active('your-decks') }> Your decks </a>
        <div class="dropdown">
            <p> Profile </p>
            <div class="dropdown-content">
                <a href={$url('./profile')} on:click={ () => set_active(null) }> View profile </a> <div class="divider"></div>
                <a href={$url('./login')}   on:click={ () => set_active(null) }> Switch account </a>
                <a href={$url('./')}        on:click={ () => set_active(null) }> Log out </a>
            </div>
        </div>
    </nav>
</header>

<div class="content">
    <slot />
</div>

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
                <li><a href="./"           on:click={ () => set_active(null) }> Home </a></li>
                <li><a href="./profile"    on:click={ () => set_active(null) }> Profile </a></li>
                <li><a href="./your-decks" on:click={ () => set_active('your-decks') }> Your decks </a></li>
                <li><a href="./community"  on:click={ () => set_active('community') }> Community </a></li>
            </ul>
            <ul class="nav_links">
                <li><a href="./archive"    on:click={ () => set_active('archive') }> Archive </a></li>
                <li><a href="./login"      on:click={ () => set_active(null) }> Switch account </a></li>
                <li><a href="./"           on:click={ () => set_active(null) }> Log out </a></li>
            </ul>                                                      
        </nav>
        <div class="column" style="width: 30%;">
            <h1> Quick search </h1>
            <input type="text" class="quick_search"/>
        </div>
    </div>
    <div class="subtext">
        <a href="./privacy-policy" on:click={ () => set_active(null) }> Privacy policy </a> <span>·</span>
        <a href="./sitemap"        on:click={ () => set_active(null) }> Sitemap        </a> <span>·</span>
        <a href="./support"        on:click={ () => set_active(null) }> Support        </a> <span>·</span>
        <p> © {copyright_year} Grip MTG Deckbuilder </p>
    </div>
</footer>
