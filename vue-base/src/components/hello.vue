<template>
    <div>
        <!-- 唯一根元素 -->
        <p> 组件:{{num}}</p>
        <div>
            <p>{{count}}</p>
            <button @click="count = count + 2">按钮</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'VueWorkHello',

    data() {
        return {
            count : 0
        };
    },
    props :{
        num:{
            type : Number,
            default:0,
        }
    },
    mounted() {
        
    },

    methods: {
        
    },
};
</script>

<style lang="scss" scoped>

</style>