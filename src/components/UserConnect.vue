<template>
    <div class="user-connect">
        <p>{{ user.email }}</p>
        <button
            @click="handleDelete"
            class="delete"
        >Delete</button>
    </div>
</template>

<script>

export default {
    name:'user-connect',
    props: {
        user:{
            type: Object,
        } 
    },
    data() {
        return{

        }
    },
    methods: {
        handleDelete(){
            var data = {
                id: this.user.id
            }
            console.log('handle delete');
            this.$emit('deleteUser',data);
        }
    }
}
</script>

<style>
    .user-connect{
        position: relative;
    }
    .user-connect .delete{
        position: absolute;
        bottom: 0px;
        right: 0px;
    }
</style>