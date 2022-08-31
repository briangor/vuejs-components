<template>
    <div class="child-comp">
        <h1 class="is-size-3">{{  msg  }}</h1>
        <br>
        <div class="container">
            <input class="input" type="text" v-model="welcomeMsg"> <br /><br />
            <button class="button" @click="changeMsg">Click to change welcome message</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChildComp',
    data() {
        return {
            welcomeMsg: "Hello"
        }
    },
    props: {
        msg: String
    },
    methods: {
        changeMsg() {
            this.$emit("changeMsg", this.welcomeMsg);
            console.log('message emit from child component')
        }
    }
}
</script>