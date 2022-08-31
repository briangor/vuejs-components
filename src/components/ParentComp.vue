<template>
    <div class="home">
        <p>This line is in parent component</p>
        <ChildComp @changeMsg="setMessage" :msg="parentMsg"/>
    </div>
</template>

<script>
import ChildComp from './ChildComp.vue';
export default {
    name: "ParentComp",
    methods: {
        setMessage(msg) {
          this.parentMsg = msg;
        }
    },
    data() {
        return {
            parentMsg: 'Hello Vue - from Parent',
        }
        
    },
    components: { ChildComp }
}
</script>

<style lang="scss">
    
</style>