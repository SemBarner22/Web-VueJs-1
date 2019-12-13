<template>
    <div class="middlePost">
    <div v-for="post in viewPosts.reverse()" :post="post" v-bind:key="post.id">
        <link rel="stylesheet" type="text/css" href="/css/post.css">
        <main>
            <article>
                <div class="title">
                    <a v-bind:href="'#page=post&id=' + post.id" @click="changePage('PostPage', post.id)">{{post.title}}</a>
                </div>
                <div class="information">{{users[post.userId].login}}</div>
                <div class="body">{{post.text}}</div>

                <ul class="attachment">
                    <li>Announcement of <a href="#">Codeforces Round #510 (Div. 1)</a></li>
                    <li>Announcement of <a href="#">Codeforces Round #510 (Div. 2)</a></li>
                </ul>
                <div class="footer">
                    <div class="left">
                        <img src="../../assets/img/voteup.png" title="Vote Up" alt="Vote Up"/>
                        <span class="positive-score">+173</span>
                        <img src="../../assets/img/votedown.png" title="Vote Down" alt="Vote Down"/>
                    </div>
                    <div class="right">
                        <img src="../../assets/img/date_16x16.png" title="Publish Time" alt="Publish Time"/>
                        2 days ago
                        <img src="../../assets/img/comments_16x16.png" title="Comments" alt="Comments"/>
                        <a href="#">{{commentsCount(comments, post).length}}</a>
                    </div>
                </div>
            </article>
        </main>
    </div>
    </div>
</template>

<script>
    export default {
        props: ['posts', 'users', 'comments'],
        name: "Index",
        computed: {
            viewPosts: function () {
                return Object.values(this.posts).sort((a, b) => a.id - b.id);
            },
        },
        methods: {
            commentsCount: function (comments, post) {
                return Object.values(comments).filter(c => c.postId === post.id);
            },
            changePage: function (page, post) {
                this.$root.$emit("onChangePage", page, post);
            },
        },

    }
</script>

<style scoped>

</style>
