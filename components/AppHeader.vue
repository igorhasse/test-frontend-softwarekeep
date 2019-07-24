<template>
    <header class="header">
        <h1 class="title">
            Store
        </h1>
        <ul>
            <li>
                <nuxt-link to='/product'>Test</nuxt-link>
                <nuxt-link to='/'>Home</nuxt-link>
                <a href="https://github.com/igorhasse" target="_blank" class="text">GitHub</a>
            </li>
        </ul>
    </header>
</template>

<script>
export default {
    name: 'AppHeader'
}
</script>

<style>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    background: #042338;
}

.header h1 {
    font-size: 12px;
    color: #fff;
    font-weight: bold;
}

.header ul {
    list-style: none;
}

.header ul li a{
    font-family: Ubuntu,sans-serif;
    font-size: 13px;
    margin: 0 15px;
    color: #fff;
    font-weight: bold;
    text-decoration: none;
}
</style>
