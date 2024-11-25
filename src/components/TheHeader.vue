<template>
    <header class="header">
       <slot></slot>
    </header>
</template>

<script>
export default {
name: 'TheHeader',
props:{
    title: String
}
}
</script>

<style>
    .header {
        background-color: #42b983;
        color: white;
        margin-bottom: 5px;
    }
</style>