<template>
    <div class="header-container">
        <header>
            <div class="header-content">
                <div class="header-logo">LOGO</div>
                <div class="header-search">
                    <SearchStroke />
                </div>
                <div class="header-buttons">
                    <UserButtons />
                </div>
                <button class="menu-button" v-on:click="displayMenu"></button>
            </div>
            <div id="#header-nav-menu" class="menu-nav">
                <div class="mobile-nav">
                    <SearchStroke />
                </div>
                <NavLinks />
                <div class="mobile-nav">
                    <UserButtons />
                </div>
            </div>
        </header>
    </div>
</template>

<script>
import NavLinks from './NavLinks.vue';
import SearchStroke from './SearchStroke.vue';
import UserButtons from './UserButtons.vue';

export default {
    name: "MyHeader",
    components: { NavLinks, SearchStroke, UserButtons },
    data() {
        return {
            ifScroll: false
        }
    },
    created() {
        window.addEventListener('scroll', this.handleScroll);
    },
    methods: {
        displayMenu(event) {
            event.preventDefault();
            let navMenu = document.getElementById("#header-nav-menu");
            navMenu.classList.toggle("menu-nav");
            navMenu.classList.toggle("display-menu");
        },
        handleScroll(event) {
            event.preventDefault();
            if (window.innerWidth > 768) {
                let navMenu = document.getElementById("#header-nav-menu"),
                    bodyRect = document.body.getBoundingClientRect(),
                    elemRect = navMenu.getBoundingClientRect(),
                    offset = elemRect.top - bodyRect.top;
                let a = setTimeout(event.pageY, 100);
                if (a < offset) {
                    navMenu.classList.remove("show-menu");
                    navMenu.classList.add("hide-menu");
                } else {
                    navMenu.classList.remove("hide-menu");
                    navMenu.classList.add("show-menu");
                }

            } else {
                let navMenu = document.getElementById("#header-nav-menu");
                navMenu.classList.remove("hide-menu");
                navMenu.classList.remove("show-menu");
            }
        }
    },
    beforeMount() {
        window.addEventListener('scroll', this.handleScroll);
    },
    unmounted() {
        window.removeEventListener('scroll', this.handleScroll);
    }
}
</script>
<style>
.header-container {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    box-shadow: 0px 1px 20px red;
}

header {
    position: relative;
    max-width: 1400px;
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
    margin: auto;
}

.header-content {
    position: relative;
    z-index: 9999;
    width: 100%;
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    background-color: #ffffff;
    box-shadow: 0px 5px 20px #ffffff;

}

.header-logo {
    display: block;
    max-width: 240px;
    width: 100%;
    height: 42px;
    border: 1px solid#f0f0f0;
    font-size: 38px;
}

.header-buttons {
    display: flex;
    margin-right: 0;
}

.header-buttons button {
    margin-left: 10px;
}

.menu-button {
    height: 42px;
    width: 50px;
    background-image: url('../assets/menu.svg');
    background-position: center;
    background-size: 60%;
    background-repeat: no-repeat;
    background-color: #ffffff;
    display: none;
}

.menu-nav {
    padding-top: 20px;
    position: relative;
}

.show-menu {
    opacity: 1;
    transition: all 0.3s linear;
}

.hide-menu,
.hide-menu nav {
    height: 0;
    padding: 0;
    margin: 0;
    opacity: 0;
    transition: all 0.3s linear;
}

.mobile-nav {
    display: none;
}

@media (max-width: 768px) {

    .header-search,
    .header-buttons {
        display: none;
    }

    .menu-button {
        display: block;
    }

    .menu-nav {
        display: none;
        height: 100vh;
    }

    .mobile-nav {
        display: flex;
    }

    .hide-menu,
    .hide-menu nav,
    .show-menu {
        height: 0;
        padding: 0;
        margin: 0;
        opacity: 0;
    }

    .dislay-menu {
        opacity: 1;
    }
    .dislay-menu .menu-nav {
        display: block;
    }
    .display-menu nav {
        display: block;
    }
}
</style>