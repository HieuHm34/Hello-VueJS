<template>
  <div id="app">
    <div class="container">
      <comp-header 
        :title="title"
        @changeTitleEvent="handleChangeTitle" 
      />
      <list-user 
        :listUser="listUser"
        @deleteUserEvent="handleDeleteUser" 
      />
      <comp-footer :title="title" />
      <demo-ref />
      <demo-slot />
    </div>
  </div>
</template>

<script>
import ListUser from './components/ListUser.vue'
import CompFooter from './components/CompFooter.vue'
import CompHeader from './components/CompHeader.vue'
import DemoRef from './components/DemoRef.vue'
import DemoSlot from './components/DemoSlot.vue'

export default {
  name: 'app',
  components: {
    CompHeader,
    ListUser,
    CompFooter,
    DemoRef,
    DemoSlot
  },
  data() {
    return {
      title: 'Hello VueJS',
      listUser: [
        { id: 100, email:"test1@gmail.com", active: true },
        { id: 101, email:"test2@gmail.com", active: false },
        { id: 102, email:"test3@gmail.com", active: true },
        { id: 103, email:"test4@gmail.com", active: false },
        { id: 104, email:"test5@gmail.com", active: true },
        { id: 105, email:"test6@gmail.com", active: false }
      ]
    }
  },
  methods:{
    handleChangeTitle(data){
      this.title = data.title;
      console.log('handleChangeTitle App.vue');
    },
    handleDeleteUser(data) {
      var indexDelete = -1;
      this.listUser.forEach((element,idx) => {
        if(element.id === data.id) indexDelete = idx
      });
      if(indexDelete != -1) {
        this.listUser.splice(indexDelete, 1);
      }
      console.log('handle delete user', data);
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

#app{
  font-family: Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container{
  max-width: 1170px;
  margin: 0px auto;
  padding: 0px 15px;
  min-height: 3000px;
}
</style>
