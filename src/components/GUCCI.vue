<template>
  <div class="container">
    <div class="row">
    <div class="col-6">
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
        { name: "F", id: 6 },
      ],
      list2: [
        // { name: "G", id: 7 },
      ],
        dragging: false,
      };
    },
    methods: {
      log: function(evt) {
      window.console.log(evt);
    }
    },
  })
</script>