<template>
  <div class="flex m-10">
    <h3>Draggable 1</h3>
    <draggable class="dragArea list-group w-full" :list="list" @change="log">
      <div
        class="list-group-item bg-gray-300 m-1 p-3 rounded-md text-center"
        v-for="element in list"
        :key="element.name"
      >
        {{ element.name }}
      </div>
    </draggable>

  
  <div class="flex m-10">
    <h3>Draggable 2</h3>
    <draggable class="dragArea list-group w-full" :list="list2" @change="log">
      <div
        class="list-group-item bg-gray-300 m-1 p-3 rounded-md text-center"
        v-for="element in list2"
        :key="element.name"
      >
        {{ element.name }}
      </div>
    </draggable>

  </div>

  <rawDisplayer class="flex m-10" :value="list" title="List 1" />

  <rawDisplayer class="flex m-10" :value="list2" title="List 2" />
  
  
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
        list: [
          { name: 'John', id: 1 },
          { name: 'Joao', id: 2 },
          { name: 'Jean', id: 3 },
          { name: 'Gerard', id: 4 },
        ],
        list2: [
        { name: "Juan", id: 5 },
        { name: "Edgard", id: 6 },
        { name: "Johnson", id: 7 }
      ],
        dragging: false,
      };
    },
    methods: {
      log(event) {
        console.log(event)
      },
    },
  })
</script>