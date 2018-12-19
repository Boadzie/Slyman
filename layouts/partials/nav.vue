<template>
    <header>
        <nuxt-link to="/" class="logo">Slyman</nuxt-link>
        <nav>
            <ul>
                <li><nuxt-link to="/">Home</nuxt-link></li>
                <li><nuxt-link to="news">News</nuxt-link></li>
                <li><nuxt-link to="gallery">Gallery</nuxt-link></li>
                <li><nuxt-link to="committee">Committee</nuxt-link></li>
                <li><nuxt-link to="about">About</nuxt-link></li>
                <li><nuxt-link to="contact">Contact</nuxt-link></li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {

}
</script>

<style>
  header {
        background: rgb(18, 20, 19);
        display: grid;
        grid-template-columns: repeat(2,auto);
    }
    .logo, li a {
        padding: 1em 2em;
        display: block;
        text-transform: uppercase;
        text-decoration: none;
        font-weight: bold;
        color: white;
        font-size: .9em;
    }
    nav {
        justify-self: right;
    }
    ul {
        list-style-type: none;
    }
    li {
        display: inline;
    }
    li a {
        padding: 1em 2em;
        display: inline-block;
        background: rgba(0,0,0,0.1);
    }
    .logo{
        font-size:15px;
        font-weight: bolder;
    }
</style>
