<template>
    <div> {{id}}</div>
<!--    <div class="post">-->
<!--        <link rel="stylesheet" type="text/css" href="/css/post.css">-->
<!--        <main>-->
<!--            <article>-->
<!--                <div class="title">{{id}}</div>-->
<!--                <div class="information">b</div>-->
<!--                <div class="body">c</div>-->
<!--                    <ul class="attachment">-->
<!--                        <li>Announcement of <a href="#">Codeforces Round #510 (Div. 1)</a></li>-->
<!--                        <li>Announcement of <a href="#">Codeforces Round #510 (Div. 2)</a></li>-->
<!--                    </ul>-->
<!--                    <div class="footer">-->
<!--                        <div class="left">-->
<!--                            <img src="img/voteup.png" title="Vote Up" alt="Vote Up"/>-->
<!--                            <span class="positive-score">+173</span>-->
<!--                            <img src="img/votedown.png" title="Vote Down" alt="Vote Down"/>-->
<!--                        </div>-->
<!--                        <div class="right">-->
<!--                            <img src="img/date_16x16.png" title="Publish Time" alt="Publish Time"/>-->
<!--                            2 days ago-->
<!--                            <img src="img/comments_16x16.png" title="Comments" alt="Comments"/>-->
<!--                            <a href="#">68</a>-->
<!--                        </div>-->
<!--                    </div>-->
<!--            </article>-->
<!--        </main>-->
<!--    </div>-->
</template>


<script>
    export default {
        data: function() {
            return {
                id: this.id,
            }
        },
        name: "PostPage",
        beforeCreate() {
            this.$root.$on("onChangePage", (page, id) => {
                this.page = page;
                this.id = id;
            });
        }
    }

</script>