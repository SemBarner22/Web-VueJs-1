<template>
    <section>
        <div class="datatable">
            <table>
                <thead>
                <tr>
                    <th>Id</th>
                    <th>Login</th>
                    <th>Name</th>
                </tr>
                </thead>
                <tbody>
<!--                    <template v-for="user in viewUsers" :user="user">-->
                        <tr v-for="u in users" v-bind:key="u.id">
                            <td>{{u.id}}</td>
                            <td>{{u.login}}</td>
                            <td>{{u.name}}</td>
                        </tr>
<!--                    </template>-->
                </tbody>
            </table>
        </div>
    </section>
</template>


<script>
    export default {
        props: ['users'],
        name: "Users",
        // computed: {
        //     viewUsers: function () {
        //         return Object.values(this.users).sort((a, b) => b.id - a.id);
        //     }
        // }
    }

</script>