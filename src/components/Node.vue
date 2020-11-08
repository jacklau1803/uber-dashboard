<template>
  <div class="node">
    <button
      :class="
        'dept' +
          (selected === node.name ||
          !node.hasOwnProperty('children') ||
          node.children.hasOwnProperty(selected)
            ? ' selected'
            : '')
      "
      @click="handler(node.name)"
      :disabled="!node.hasOwnProperty('children')"
    >
      {{ node.name }}
    </button>
    <p class="leader">{{ node.position }}: {{ node.leader }}</p>
  </div>
</template>

<script>
export default {
  name: "Node",
  props: {
    node: Object,
    handler: Function,
    selected: String
  },
  methods: {
    mounted() {
      console.log(this.node);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.node {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0.2rem;
}

.dept {
  display: block;
  background-color: hsl(204, 86%, 53%);
  width: 150px;
  height: 80px;
  color: white;
  font-weight: bold;
  font-size: 14.5px;
  text-align: center;

  border-radius: 4px;
}

.selected {
  background-color: hsl(141, 53%, 53%);
}

.leader {
  display: block;
  background-color: grey;
  width: 150px;
  height: 12px;
  font-size: 10px;
  color: white;
  border-radius: 4px;
}
</style>
