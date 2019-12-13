<template>
    <div class="middle">
<!--        <Sidebar/>-->
<!--        <aside>-->
<!--            <SidebarPost v-for="post in viewPosts" :post="post" :users="users" :key="post.id"/>-->
<!--        </aside>-->
        <Sidebar :users="users" :posts="posts"/>
        <main>
            <Index v-if="page === 'Index'" :posts="posts" :users="users" :comments="comments"/>
            <Enter v-if="page === 'Enter'"/>
            <Users v-if="page === 'Users'" :users="users"/>
            <PostPage v-if="page === 'PostPage'" :post="posts[this.post]" :comments="postComments" :users="users"/>
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
    import Sidebar from "./Sidebar";

    export default {
        name: "Middle",
        props: ['users', 'posts', 'comments'],
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
            Sidebar,
        }, beforeCreate() {
            this.$root.$on("onChangePage", (page, post) => {
                this.page = page;
                this.post = post;
            });
        }
    }
</script>

<style scoped>

</style>
