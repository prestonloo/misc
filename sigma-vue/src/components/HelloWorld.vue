<template>
  <div ref="container" id="container">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import sigma from "sigma";
export default {
  mounted: function() {
    this.loadGraph();
  },
  methods: {
    loadGraph() {
      /*
      var i,
        N = 10,
        E = 20,
        g = { nodes: [], edges: [] };

      for (i = 0; i < N; i++)
        g.nodes.push({
          id: "n" + i,
          label: "Node " + i,
          x: Math.random(),
          y: Math.random(),
          size: 10,
          color: "#666"
        });

      for (i = 0; i < E; i++)
        g.edges.push({
          id: "e" + i,
          source: "n" + ((Math.random() * N) | 0),
          target: "n" + ((Math.random() * N) | 0),
          size: Math.random(),
          color: "#ccc"
        });

      new sigma({
        graph: g,
        container: this.$refs["container"]
      });
      */
      var s = new sigma(this.$refs["container"]);
      s.graph
        .addNode({
          id: "n0",
          label: "Node A",
          x: 0,
          y: 0,
          size: 1,
          color: "#f00"
        })
        .addNode({
          id: "n1",
          label: "Node B",
          x: 1,
          y: 1,
          size: 1,
          color: "#00f"
        })
        .addEdge({
          id: "e0",
          source: "n0",
          target: "n1"
        });
      s.refresh();
    }
  },
  name: "HelloWorld",
  props: {
    msg: String
  }
};
</script>

<style scoped>
#container {
  position: absolute;
  width: 500px;
  height: 500px;
}
</style>
