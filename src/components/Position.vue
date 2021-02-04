<template>
    <div 
        ref="parent" class="parent"
        @touchmove="onTouchMove"
        @touchstart="onTouchStart"
        @touchEnd="onTouchEnd"
    >
        <div ref="child" class="child">
            child
        </div>
    </div>
    <input v-model="x" type="number">
    <input v-model="y" type="number">
</template>
<script>
export default {
    data() {
        return {
            x: 0,
            y: 0,
            
        }
    },
   
    beforeUpdate() {
        let child = this.$refs.child;
        child.style.top = this.y + 'px';
        child.style.left = this.x + 'px';
    },
    methods: {

        onTouchMove(e) {
            console.log('on-touch-move');
            console.log(e);
        },
        onTouchStart(e) {
            console.log('on-touch-start');
            console.log(e);
        },
        onTouchEnd(e) {
            console.log('on-touch-end');
            console.log(e);
        },

        onLongTouch() {

        }
    }
}
</script>
<style scoped>
.parent{
    background-color: red;
    width: 800px;
    height: 500px;
    position: relative;

}

.child {
    position:absolute;
    background-color: blue;
    
}
</style>