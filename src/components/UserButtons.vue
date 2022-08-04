<template>
    <div class="user-buttons">
        <button class="callback-button">Обратный звонок</button>
        <button class="profile-button"></button>
    </div>
</template>

<script>
    export default {
        name: 'UserButtons'
    }
</script>

<style>
.user-buttons {
    display: inline-flex;
    flex-direction: row;
    justify-items: center;
}
    .profile-button {
    background-color: #f0f0f0;
    background-image: url(../assets/user.svg);
    background-size: 24px;
    background-repeat: no-repeat;
    background-position: center;
    height: 42px;
    width: 50px;
    border: 1px solid lightgray;
    border-radius: 5px;
    margin-top: 0;
}

.callback-button {
    background-color: #f0f0f0;
    height: 42px;
    width: auto;
    border: 1px solid lightgray;
    border-radius: 5px;
    padding: 3px 20px;
    font-size: 18px;
}
</style>