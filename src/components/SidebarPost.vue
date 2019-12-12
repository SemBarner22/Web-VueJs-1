<template>
    <section>
        <div class="header">
            By {{users[post.userId].login}}
        </div>
        <div class="body">
            {{post.text}}
        </div>
        <div class="footer">
            // /{{post.id}}
            <a href="#page=PostPage" @click="changePage('PostPage/{{post.id}}', post.id)">View all</a>
        </div>
    </section>

</template>

<script>
    export default {
        props: ['users', 'post'],
        name: "SidebarPost",
        methods: {
            changePage: function (page, id) {
                this.$root.$emit("onChangePage", page, id);
            }, logout: function() {
                this.$root.$emit("onLogout");
                this.changePage('Index');
            }
        }
    }
</script>

<style scoped>

</style>
