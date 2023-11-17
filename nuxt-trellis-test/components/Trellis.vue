<script setup>
import { onMounted, ref } from 'vue';

// With just plain Vue, both `Force` and `WebGL` can be imported with no issues.
import * as Force from '@sayari/trellis/layout/force';
import * as WebGL from '@sayari/trellis/renderers/webgl';
console.info("Force:", Force); // DEBUG
console.info("WebGL:", WebGL); // DEBUG

const NODE_STYLE = { color: '#999', stroke: [{ color: '#FFF', width: 2 }, { color: '#F7CA4D', width: 2 }] }
const EDGE_STYLE = { arrow: 'forward', width: 2, stroke: '#CCC' }
let nodes = ['a', 'b', 'c', 'd', 'e', 'f']
  .map((id) => ({ id, radius: 18, style: NODE_STYLE }));
let edges = [['a', 'b'], ['a', 'c'], ['a', 'd'], ['c', 'e'], ['c', 'f']]
  .map(([source, target]) => ({
    id: `${source}_${target}`,
    source,
    target,
    style: EDGE_STYLE,
  }));

const trellisContainer = ref();

onMounted(() => {
  const renderer = WebGL.Renderer({ container: trellisContainer.value });
  const force = Force.Layout();

  const render = () => {
    renderer({
      nodes,
      edges,
      options: renderOptions,
    });
  };

  const renderOptions = {
    width: trellisContainer.value.offsetWidth,
    height: trellisContainer.value.offsetHeight,
    onNodePointerEnter: ({ target: { id } }) => {
      nodes.find((node) => node.id === id).style.stroke[1].width = 4;
      render();
    },
    onNodePointerLeave: ({ target: { id } }) => {
      nodes.find((node) => node.id === id).style.stroke[1].width = 2;
      render();
    },
    onNodeDrag: ({ nodeX: x, nodeY: y, target: { id } }) => {
      const node = nodes.find((node) => node.id === id);
      node.x = x;
      node.y = y;
      render();
    },
    onViewportDrag: ({ viewportX, viewportY }) => {
      renderOptions.x = viewportX;
      renderOptions.y = viewportY;
      render();
    },
  };

  // Run layout and render graph
  force({
    nodes,
    edges,
  }).then((graph) => {
    nodes = graph.nodes;
    render();
  });
});
</script>

<template>
  <div class="trellis-container" ref="trellisContainer"></div>
</template>

<style scoped>
.trellis-container {
  background-color: #eee;
  border: 1px solid #666;
  height: 400px;
  width: 600px;
}
</style>