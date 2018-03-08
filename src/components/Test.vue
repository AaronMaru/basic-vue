<template id="">
    <div class="test">
        <input type="text" v-model="title">
        <h1>{{title}}</h1>
        <p>{{user.firstName}}</p>
        <p v-text="user.lastName"></p>
        <p v-if="showName">{{user.lastName}}</p>
        <p v-else>DD</p>
        <ul>
            <li v-for="item in items">{{item.title}}</li>
        </ul>
        <button @click="greet">Say Greeting</button>
        <input type="text" v-on:keyup="presskey">

        <hr>
        <label for="">firstName</label><input type="text" v-model="user.firstName">
        <label for="">lastName</label><input type="text" v-model="user.lastName">
        <h3>{{fullName}}</h3>
        <h2>{{msg}}</h2>
    </div>
</template>

<script>
    export default {
        name: 'test',
        props:{
                msg: {
                    type: String,
                    default: 'Foobar'
                }
        },
        data: function() {
            return{
                title: 'hello world',
                user: {
                    firstName: 'Aaron',
                    lastName: 'Maru'
                },
                showName: false,
                items: [
                    {title: 'Item One'},
                    {title: 'Item Two'},
                    {title: 'Item Three'}
                ]
            }
        },
        methods: {
            greet: function(){
                alert("Marudd");
            },
            presskey: function(e){
                console.log(e.target.value);
            }
        },
        computed: {
            fullName: function(){
                return this.user.firstName + ' ' + this.user.lastName;
            }
        }
    }
</script>

<style scoped>

</style>
