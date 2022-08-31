<template>
    <div class="home">
        <ChildComp @changeMsg="setMessage" :msg="welcomeMsg"/>
    </div>
</template>

<script>
import ChildComp from './ChildComp.vue';
export default {
    name: "ParentComp",
    methods: {
        setMessage(msg) {
          this.welcomeMsg = msg;
        }
    },
    data() {
        return {
            welcomeMsg: "Hello Vue"
        }
        
    },
    components: { ChildComp }
}
</script>

<style lang="scss">
    
</style>