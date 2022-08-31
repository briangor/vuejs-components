<template>
    <div class="child-comp">
        <h4 class="is-size-3">{{  msg  }}</h4>
        <br>
        <div class="container">
            <input class="input" type="text" v-model="childMsg"> <br /><br />
            <button class="button" @click="changeMsg">Click to change welcome message</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ChildComp',
    data() {
        return {
            childMsg: "Hello - from Child"
        }
    },
    props: {
        msg: {
            type: String,
            required: true
        },
    
    },
    methods: {
        changeMsg() {
            this.$emit("changeMsg", this.childMsg);
            console.log('message emit from child component')
        }
    }
}
</script>