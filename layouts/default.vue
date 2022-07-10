<script setup lang="ts">
import { feedsInfo } from '~/composables/api'

</script>

<template>
    <div>
        <header class="header">
            <nav class="inner" role="navigation">
                <NuxtLink to="/" exact>
                    <img class="logo" src="/logo.svg" alt="logo">
                </NuxtLink>
                <NuxtLink v-for="(list, key) in feedsInfo" :key="key" :to="`/${key}`">
                    {{ list.title }}
                </NuxtLink>
                <a class="github" href="https://github.com/nuxt/hackernews" target="_blank" rel="noopener banner">
                    Built with Nuxt3
                </a>
            </nav>
        </header>
        <slot role="main" />
    </div>
</template>

<style>
body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
    font-size: 15px;
    background-color: white;
    margin: 0;
    padding: 0;
    color: #2E495E;
    overflow-y: scroll;
}

a {
    color: #2E495E;
    text-decoration: none;
}

.header {
    background-color: #2E495E;
    z-index: 999;
    height: 55px;
}

.header .inner {
    max-width: 800px;
    box-sizing: border-box;
    margin: 0px auto;
    padding: 12px 5px;
    display: flex;
    place-items: center;
}

.header a {
    color: #fff;
    line-height: 24px;
    transition: color 0.15s ease;
    display: inline-block;
    vertical-align: middle;
    font-weight: 300;
    letter-spacing: 0.075em;
    margin-right: 1.8em;
}

.header a:hover {
    color: #fff;
}

.header a.router-link-active,
.header a.nuxt-link-active {
    color: #fff;
    font-weight: 600;
}

.header a:nth-child(6) {
    margin-right: 0;
}

.header .github {
    color: #fff;
    font-size: 0.9em;
    margin: auto;
    text-align: right;
    flex-grow: 1;
}

.logo {
    width: 30px;
    height: 30px;
    margin-right: 10px;
    display: inline-block;
    vertical-align: middle;
}

.view {
    max-width: 800px;
    margin: 0 auto;
    position: relative;
}

.appear-active {
    transition: opacity 0.4s ease;
}

.appear {
    opacity: 0;
}

@media (max-width: 860px) {
    .header .inner {
        padding: 15px 30px;
    }
}

@media (max-width: 600px) {
    .header .inner {
        padding: 15px;
    }

    .header a {
        margin-right: 1em;
    }

    .header .github {
        display: none;
    }
}
</style>
