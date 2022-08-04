<template>
    <nav>
        <ul>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
            <li><a href="/">Link</a></li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'NavLinks'
}
</script>

<style>
nav {
    display: flex;
    margin: 20px auto;
    width: 100%;
}
nav ul {
    text-decoration: none;
    list-style-type: none;
}
nav ul li {
    line-height: 24p;
    display: inline;
}
a {
    font-size: 24px;
    margin-right: 5%;
    color: #000;
}
@media (max-width: 768px) {
    nav ul li {
        display: list-item;
        line-height: 32px;
    }
    nav {
        display: none;
    }
}
</style>