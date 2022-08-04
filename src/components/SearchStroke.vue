<template>
    <div class="search-stroke">
        <input class="search-field" type="text" placeholder="Search..." />
        <button class="search-button" />
    </div>
</template>

<script>
export default {
    name: 'SearchStroke'
}
</script>

<style>
.search-stroke {
    min-width: 300px;
    max-height: 42px;
    display: inline-flex;
    justify-content: center;
    vertical-align: middle;
}

.search-field {
    padding: 5px 10px;
    box-sizing: border-box;
    background-color: #f0f0f0;
    border-radius: 5px 0 0 5px;
    width: 100%;
    ;
}

.search-button {
    width: 48px;
    height: 42px;
    margin: auto auto auto 0;
    background-color: #f0f0f0;
    background-image: url(../assets/search.svg);
    background-size: 60%;
    background-repeat: no-repeat;
    background-position: center;
    border-radius: 0 5px 5px 0;
    border-left: 2px solid gray;
}
</style>