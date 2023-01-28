<template>
    <div class="title-layer">
        <h4>{{ rooms[useIndex].title}}</h4>
        <img class="room-image" :src="rooms[useIndex].image" />
        <h4>{{ rooms[useIndex].content}}</h4>
        <h4>{{ rooms[useIndex].price}}</h4>
        <button @click="close">닫기</button>
    </div>
</template>

<script>

    export default {
        name : "RoomDetail",
        props : {
            rooms : Object,
            useIndex : null
        },
        methods : {
            close : function () {
                return this.$emit('modalClose', false)
            }
        },
        mounted () {
            console.log("Rooms Details get Use Index : " , this.useIndex)
        }
    }

</script>

<style scoped>
.title-layer {
    margin: 0 auto;
    width: 100%;
    border: 2px solid rgb(230, 247, 199);
    border-radius: 2px solid rgba(231, 33, 33, 0.836);
    margin-bottom: 10px;
}
.room-image {
    widows: 50%;
}
</style>