<template>
    <header>
        <h1>
            {{ title }}
            <br>
            <button @click="changeTitleHeader">Change title from button</button>
        </h1>
    </header>
</template>

<script>
export default {
    name: 'comp-header',
    props:{
        title: String
    },
    data(){
        return{

        }
    },
    methods:{
        changeTitleHeader(){
            //Khong duoc phep thay doi truc tiep props tu component cha (bao loi tai consolog tren web)
            //Truyen su kien thay doi ra ben ngoai (o day la component App.vue)
            var data = {
                title: 'Chào mừng các bạn đến với VueJS'
            }
            this.$emit('changeTitleEvent', data)
        }
    }
}
</script>

<style>

</style>