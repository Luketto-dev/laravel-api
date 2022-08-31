<template>
    <div>  
        <Navbar></Navbar>
        <div class="container">
            <h1>{{message}}</h1>
        </div>
        <PostsList></PostsList>
    </div>     
</template>

<script>
import Navbar from "./frontend/components/Navbar.vue";
import PostsList from "./frontend/components/PostsList.vue";
export default {
    components: { Navbar, PostsList },
    data() {
        return {
            message: "Hello Vuejs"
        };
    },
    components: { Navbar, PostsList }
}
</script>

<style>

</style>