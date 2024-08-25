<script>
export default {
    data() {
        return {
            navLinkNames:[
                {
                    label: "Homepage",
                    name:"home",
                },                {
                    label: "Project list",
                    name:"projects",
                },                {
                    label: "Aboutpage",
                    name:"about",
                }
            ]
        }
    }
}
</script>

<template>

<nav class="d-flex">
    <ul class="list-style-none d-flex">
        <li class="me-3" v-for="navItem in navLinkNames">
            <router-link :to="{name: navItem.name}">{{navItem.label}}</router-link>
        </li>
    </ul>
</nav>
</template>

<style scoped lang="scss">
*{
    color: white;
    list-style-type: none;
}
</style>