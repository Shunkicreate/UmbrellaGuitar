<template>
  <div class="container">
    <div class="row">
      <div class="col-6">
        <h3 align="center">V.vue</h3>

      <div>親要素にdisplay: flexのスタイルを適用すると、親要素はflex containerとなり、子要素はflex itemとなります。</div>
      <div>div要素はブロック要素ですので、本来は１つのdivごとに改行されますが、flex itemとなっているので、横並びで表示されています。</div>
      

        <div style="display: flex; justify-content: center;">
          <div style="width: 300px; height: 400px; background-color: gray;">
            <h3>ブロック１</h3>

            

          </div>
          <div style="width: 300px; height: 400px;">
            <h3></h3>
          </div>

          <div style="width: 300px; height: 400px; background-color: gray;">
            <h3>ブロック3</h3>
          </div>
        </div>
    
       
        <draggable class="-listgroup" :list="list1" :group="{name: 'people',  pull: 'clone',put: false}" @change="log">

        <div
          class="list-group-item"
          v-for="(element) in list1"
          :key="element.name"
        >
          {{ element.name }} 
        </div>
      </draggable>
    </div>

    <div class="col-6">
      
      <draggable class="list-group" :list="list2" group="people" @change="log">
        <div
          class="list-group-item"
          v-for="(element) in list2"
          :key="element.name"
        >
          {{ element.name }} 
        </div>
      </draggable>
    </div>
  </div>
  </div>


    <rawDisplayer class="col-6" :value="list1" title="List 1"/>

    <rawDisplayer class="col-6" :value="list2" title="List 2"/> 
</template>



<script>
  import { defineComponent } from 'vue'
  import { VueDraggableNext } from 'vue-draggable-next'
  let id = 1;
  export default defineComponent({
    name: "GUCCI",
    display: "GUCCI",
    order: 1,
    components: {
      draggable: VueDraggableNext
    },
    data() {
      return {
        enabled: true,
        list1: [[
        { name: "A", id: 1 },
        { name: "B", id: 2 },
        { name: "C", id: 3 },
        { name: "D", id: 4 },
        { name: "E", id: 5 },
        { name: "F", id: 6 }
      ],[
        { name: "G", id: 1 },
        { name: "H", id: 2 },
        { name: "I", id: 3 },
        { name: "J", id: 4 },
        { name: "K", id: 5 },
        { name: "L", id: 6 }]],
        dragging: false,
      };
    },
    methods: {
      log: function(evt) {
      window.console.log(evt);
    }
    }
  });
</script>