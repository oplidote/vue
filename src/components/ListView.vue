<template>
    <div 
    class="card mt-2" 
    v-for="(item,index) in items" 
    v-bind:key="item.id"
    >
        <!-- 반복 내용영역 -->
        <slot :item="item" :index="index"></slot>
    </div>
</template>

<script>
export default {
    props: {
        items: {
            type: Array,
            require: true,
        }
    }
}
</script>

<style>

</style>