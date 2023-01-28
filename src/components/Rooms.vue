<template>

    <div v-for="item in rooms" :key="item">
        <img :src="item.image" />
        <h4 class="item-title" @click="open(item.id)"> {{ item.title }}</h4>
        <p>Price : {{ item.price }} 원</p>
    </div>

</template>

<script>
    export default {
        name : "Rooms",
        props : {
            rooms : Object
        },
        methods: {
            open: function (useIndex) {
                return this.$emit('modalOpen', useIndex)
            }
        },

        
    }
</script>

<style scoped>
.item-title {
    cursor: pointer;
}
</style>