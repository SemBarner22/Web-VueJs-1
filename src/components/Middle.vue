<template>
    <div class="middle">
<!--        <Sidebar/>-->
<!--        <aside>-->
<!--            <SidebarPost v-for="post in viewPosts" :post="post" :users="users" :key="post.id"/>-->
<!--        </aside>-->
        <main>
            <Index v-if="page === 'Index'" :posts="posts"/>
            <Enter v-if="page === 'Enter'"/>
            <Users v-if="page === 'Users'" :users="users"/>
            <PostPage v-if="page === 'PostPage'" :id="4"/>
            <Register v-if="page === 'Register'"/>
            <AddPost v-if="page === 'AddPost'"/>
            <EditPost v-if="page === 'EditPost'"/>
        </main>
    </div>
</template>
<script>
    import Index from './middle/Index';
    import Users from './middle/Users';
    import Enter from './middle/Enter';
    import Register from './middle/Register';
    import AddPost from './middle/AddPost';
    import EditPost from "./middle/EditPost";
    import PostPage from "./middle/PostPage";

    export default {
        name: "Middle",
        props: ['users', 'posts'],
        data: function () {
            return {
                page: "Index"
            }
        },
        // computed: {
        //     viewPosts: function () {
        //         return Object.values(this.posts).sort((a, b) => b.id - a.id).slice(0, 2);
        //     }
        // },
        components: {
            PostPage,
            EditPost,
            Index,
            Enter,
            Register,
            AddPost,
            Users,
        }, beforeCreate() {
            this.$root.$on("onChangePage", (page, id) => {
                this.page = page;
                this.id = id;
            });
        }
    }
</script>

<style scoped>

</style>
