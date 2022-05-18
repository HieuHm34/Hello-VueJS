<template>
  <div class="demo-slot">
      <comp-tabs title="Tiêu đề của Tab">
          <ul class="tab-header">
              <li 
                v-for="(tabHeader, index) in tabHeaders" 
                :key="index"
                @click="setActiveTab(index)"
                :class="{ active: tabActive == index }"
              >
                  {{ tabHeader.text }}
              </li>
          </ul>
          <div class="tabs-content tab1" v-if="tabActive == 0">
              <p>Tab 1 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Omnis, quisquam expedita vel maiores quis sapiente quas tenetur dolorem labore. Debitis natus voluptatibus nesciunt ducimus consequatur totam esse repudiandae corporis dolor.</p>
          </div>
          <div class="tabs-content tab2" v-else-if="tabActive == 1">
              <p>Tab 2 Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates dicta sint ullam porro vero! Voluptatem molestiae optio nesciunt, ducimus eveniet, nulla, ab laboriosam quas mollitia ullam suscipit cumque pariatur nam.</p>
          </div>
          <div class="tabs-content tab3" v-else>
              <p>Tab 3 Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates dicta sint ullam porro vero! Voluptatem molestiae optio nesciunt, ducimus eveniet, nulla, ab laboriosam quas mollitia ullam suscipit cumque pariatur nam.</p>
          </div>
      </comp-tabs>
  </div>
</template>

<script>
import CompTabs from './CompTabs.vue'

export default {
    name: "demo-slot",
    components: { CompTabs },
    
    data(){
        return{
            tabHeaders:[
                { text:'Tab1'},
                { text:'Tab2'},
                { text:'Tab3'},
            ],
            tabActive: ''
        }
    },
    methods: {
        setActiveTab(index) {
            this.tabActive = index
        }
    }
}
</script>

<style>
    .demo-slot{
        margin-top: 80px;
        padding: 100px 30px;
        border: 1px solid #000;
    }
</style>