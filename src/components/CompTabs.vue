<template>
  <div class="comp-tabs">
      <div class="tab-title">
          <span>{{ title }}</span>
            <svg width='16' height='16' style='background: none'>
            <circle cx='8' cy='8' r='8' fill='blue' stroke='orange' stroke-width='1' fill-opacity='0.5'/>
            </svg>
      </div>
      <div class="tab-content">
          <slot></slot>
      </div>
  </div>
</template>

<script>
export default {
    name: 'comp-tabs',
    data(){
        return{

        }
    },
    props:{
        title:String
    },    
}
</script>

<style>
    .tab-title{
        padding: 15px 30px;
        display: flex;
        justify-content: space-between;
        border: 2px solid #000;
    }

    .tab-content {
        border: 2px solid blue;
        margin-top: 2px;
        padding: 2px;
    }

    .tab-header{
        list-style: none;
        margin: 0px;
        padding: 0px;
        display: flex;
    }

    .tab-header li {
        padding: 8px 15px;
        background-color: #ccc;
        transition: all .3s ease;
    }

    .tab-header li:hover{
        background-color: #333;
        color: #000;
    }

    .tabs-content {
        border: 2px solid green;
        padding: 15px;
        margin: 10px auto;
        text-align: left;
    }
</style>