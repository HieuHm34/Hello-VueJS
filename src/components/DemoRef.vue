<template>
  <div class="demo-ref">
      <h1>DemoRef</h1>
      <button 
        class="avatar"
        @click="handleClickInputAvatar"
      >Thay đổi Avatar</button>
      <input
        ref="fileInputAvatar"
        type="file"
        style="display: none;"
      >
  </div>
</template>

<script>
export default {
    name: "demo-ref",
    data(){
        return {

        }
    },

    methods: {
        handleClickInputAvatar(){
            this.$refs.fileInputAvatar.click()
        }
    }
}
</script>

<style>
    .demo-ref{
        margin-top: 100px;
        padding: 100px 30px;
        border: 1px solid #000;
    }

    .avatar{
        color: #fff;
        background-color: #333;
        border: 2px solid #333;
        padding: 12px 15px;
    }

    .avatar:hover {
        background-color: #fff;
        color: #333;
    }
</style>