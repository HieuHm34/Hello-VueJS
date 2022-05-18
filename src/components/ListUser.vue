<template>
    <div class="list-user">
        <user-connect 
            v-for="user in listUser" 
            :key="user.id" 
            :user="user"
            @deleteUser="deleteUser"
        />
    </div>
</template>

<script>
/* Mô hình:
App -> chứa arr ListUser props down xuống cho các component con
    ListUser -> Không được quyền thay đổi arr ListUser -> lại truyền event ra cho component cha (App.vue)
        User -> Chỉ truyền Event thông báo ra cho component cha (ListUser)
        User



*/

import UserConnect from './UserConnect.vue'

export default {
    name: 'list-user',
    data() {
        return{

        }
    },
    props: {
        listUser: {
            type: Array,
            default: () => []
        }
    },
    components: { UserConnect },

    methods:{
        deleteUser(data) {
            console.log('Delete user done',data);
            this.$emit('deleteUserEvent', data);
        }
    }
}
</script>

<style>
    .list-user {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    .list-user .user-connect {
        padding: 30px;
        margin-bottom: 30px;
        border: 1px solid #333;
        width: calc(33.3333% - 20px);
    }

</style>