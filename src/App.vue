<template>
  <h3>Draggable</h3>

  <draggable
    :list="list"
    item-key="name"
    class="list-group"
    ghost-class="ghost"
    drag-class="dragging-element"
    :move="checkMove"
    @start="dragging = true"
    @end="dragging = false"
    :class="{ dragging }"
  >
    <template #item="{ element }">
      <div class="list-group-item draggable">
        <p>{{ element.name }}</p>
        <div class="hidden-in-dragging">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem
          veniam eaque laborum earum accusantium voluptatem, harum nemo, nobis
          officiis voluptate ducimus. Modi natus dolorum iusto maxime, alias
          veniam eius. Iure.
        </div>
      </div>
    </template>
  </draggable>
</template>

<script>
import draggable from "vuedraggable";
let id = 1;
export default {
  name: "simple",
  display: "Simple",
  order: 0,
  components: {
    draggable,
  },
  data() {
    return {
      list: [
        { name: "John", id: 0 },
        { name: "Joao", id: 1 },
        { name: "Jean", id: 2 },
      ],
      dragging: false,
    };
  },
};
</script>
<style scoped>
.buttons {
  margin-top: 35px;
}
.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}
.draggable {
  cursor: pointer;
}
.list-group-item {
  border: 1px solid black;
  padding: 3px;
  margin-top: 5px;
}
.dragging-element .hidden-in-dragging,
.dragging .hidden-in-dragging {
  display: none;
}
</style>
