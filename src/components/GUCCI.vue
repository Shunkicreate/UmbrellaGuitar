<template>
  <div>
    <!-- :disabled="isDrag" でDnDは禁止できる -->
    <button @click="replace">初期化</button>
    <button @click="reset">リセット</button>

    <div style="display: flex; justify-content: center">
      <div class="waku" style="margin: 0 100px">
        <div>
          <h3 align="center">List1</h3>
        </div>

        <div>
          <draggable
            class="-listgroup"
            :list="list1"
            :group="{ name: 'people', pull: 'clone', put: false }"
            @change="log"
            :options="{ animation: 200 }"
            @dragenter="dragenter(fruit)"
          >
            <div
              class="list-group-item"
              v-for="element in list1"
              :key="element.name"
            >
              {{ element.name }}
            </div>
          </draggable>
        </div>
      </div>
      <div class="waku">
        <div>
          <h3 align="center">List2</h3>
        </div>

        <div>
          <draggable
            class="list-group"
            :list="list2"
            group="people"
            @change="log"
          >
            <div
              class="list-group-item"
              v-for="element in list2"
              :key="element.name"
            >
              {{ element.name }}
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
import { defineComponent } from "vue";
import { VueDraggableNext } from "vue-draggable-next";
let id = 1;
export default defineComponent({
  name: "GUCCI",
  display: "GUCCI",
  order: 1,
  components: {
    draggable: VueDraggableNext,
  },
  data() {
    return {
      enabled: true,
      list1: [
        { name: " A ", id: 1 },
        { name: " B ", id: 2 },
        { name: " C ", id: 3 },
        { name: " D ", id: 4 },
        { name: " E ", id: 5 },
        { name: " F ", id: 6 },
      ],

      list2: [
        { name: " G ", id: 1 },
        { name: " H ", id: 2 },
        { name: " I ", id: 3 },
        { name: " J ", id: 4 },
        { name: " K ", id: 5 },
        { name: " L ", id: 6 },
      ],
      dragging: false,
    };
  },
  methods: {
    replace: function () {
      this.list1 = [
        { name: " A ", id: 1 },
        { name: " B ", id: 2 },
        { name: " C ", id: 3 },
        { name: " D ", id: 4 },
        { name: " E ", id: 5 },
        { name: " F ", id: 6 },
      ];
    },
    onclone: (e) => {
      console.log("onclone");
    },
    reset: function () {
      this.list2 = [];
    },
    dragenter(item) {
      this.replace;
    },
    log: function (evt) {
      window.console.log(evt);
    },
  },
});
</script>

<style>
  .waku {
    box-shadow: 3px 3px 3px #a5aaabe5;
    margin: 10%;
    padding: 10%;
  }
</style>