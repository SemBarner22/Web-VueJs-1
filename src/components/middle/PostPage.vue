<template>
    <div class="post">
        <link rel="stylesheet" type="text/css" href="/css/post.css">
        <main>
            <div class="title">{{post.title}}</div>
            <div class="information"></div>
            <div class="body">{{post.text}}</div>
            <article>
                    <ul class="attachment">
                        <li>Announcement of <a href="#">Codeforces Round #510 (Div. 1)</a></li>
                        <li>Announcement of <a href="#">Codeforces Round #510 (Div. 2)</a></li>
                    </ul>
            </article>
        </main>
    </div>
</template>


<script>
    export default {
        name: "Index",
        props: ['post', 'comments', 'users'],
    }

</script>