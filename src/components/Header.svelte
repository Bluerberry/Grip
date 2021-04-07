<script>
    import { url, isActive } from '@roxi/routify';
</script>

<style>
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
        background-color: #E4DED6;
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
</style>

<header>
    <nav>
        <a href={$url('./')}           id="title"      class="title"> Grip </a>
        <a href={$url('./archive')}    id="archive"    class="menu_item" class:active={$isActive('./archive')}> Archive </a>
        <a href={$url('./community')}  id="community"  class="menu_item" class:active={$isActive('./community')}> Community </a>
        <a href={$url('./your-decks')} id="your-decks" class="menu_item" class:active={$isActive('./your-decks')}> Your decks </a>
        <div class="dropdown">
            <p> Profile </p>
            <div class="dropdown-content">
                <a href={$url('./profile')}> View profile </a> <div class="divider"></div>
                <a href={$url('./login')}> Switch account </a>
                <a href={$url('./')}> Log out </a>
            </div>
        </div>
    </nav>
</header>