<template>
    <header class="header"></header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style>
    .header{
        grid-area: header;
        background: linear-gradient(to right, #308509, #42ee76);

        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>