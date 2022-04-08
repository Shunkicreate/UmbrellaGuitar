<template>
  <div class="container">
    <div class="row">
    <div class="col-6">
    
      <div class="btn-group list-group-item" role="group">
            <button class="btn btn-secondary" @click="replace">List1の順番をもとに戻す</button>
          </div>

          <div class="btn-group list-group-item" role="group">
            <button class="btn btn-secondary" @click="reset">List2を削除</button>
          </div>

      <h3 align="center">List1</h3>
       
      <draggable class="list-group" :list="list1" :group="{name: 'people',  pull: 'clone',put: false}" @change="log">

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
      <h3 alig="center">List2</h3>
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
</template>



<script>
  import { defineComponent } from 'vue'
  import { VueDraggableNext } from 'vue-draggable-next'
  let id = 1;
  export default defineComponent({
    name: "GUCCI",
    display: "GUCCI",
    order: 2,
    components: {
      draggable: VueDraggableNext
    },
    data() {
      return {
        enabled: true,
        list1: [
        { name: "A", id: 1 },
        { name: "B", id: 2 },
        { name: "C", id: 3 },
        { name: "D", id: 4 },
        { name: "E", id: 5 },
        { name: "F", id: 6 }
      ],
      list2: [
        //空
      ],
        dragging: false,
      };
    },
    methods: {
      replace: function() {
      this.list1 = [{ name: "A", id: 1 },
        { name: "B", id: 2 },
        { name: "C", id: 3 },
        { name: "D", id: 4 },
        { name: "E", id: 5 },
        { name: "F", id: 6 }];
    },
    reset: function(){
      this.list2 = []
    },
      log: function(evt) {
      window.console.log(evt);
    }
    }
  });
</script>