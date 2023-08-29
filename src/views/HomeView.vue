<script setup>
import Square from "@/components/Square.vue";
</script>

<template>
  <div class="planet-wrap">
    <div class="circle-container">
      <Square
        v-for="(position, index) in usedPositions"
        :key="index"
        :color="position.color"
        :style="{
          position: 'absolute',
          transform: `translate(${position.x}px, ${position.y}px)`,
        }"
      />
    </div>
  </div>
</template>

<script>
export default {
  components: {
    Square,
  },
  data() {
    return {
      squares: [
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      { color: "#B2ACA5" },
      { color: "#928980" },
      { color: "#6F7975" },
      { color: "#726873" },
      { color: "#BCBAB6" },
      ],
      usedPositions: [],
    };
  },
  // methods: {
  //   getPosition(index) {
  //     let isOverlap = false;
  //     let x = 0;
  //     let y = 0;
  //     let attempt = 0;

  //     do {
  //       if (attempt > 20) {
  //         // 避免无限循环
  //         break;
  //       }

  //       const total = this.squares.length;
  //       const angle = (360 / total) * index;
  //       const maxRadius = 300;
  //       const minRadius = 50;

  //       const radius = Math.random() * (maxRadius - minRadius) + minRadius;
  //       x = Math.cos((angle * Math.PI) / 180) * radius;
  //       y = Math.sin((angle * Math.PI) / 180) * radius;

  //       isOverlap = this.usedPositions.some((pos) => {
  //         return Math.abs(pos.x - x) < 10 && Math.abs(pos.y - y) < 10;
  //       });

  //       attempt++;
  //     } while (isOverlap);

  //     this.usedPositions.push({ x, y });

  //     return {
  //       position: "absolute",
  //       transform: `translate(${x}px, ${y}px)`,
  //     };
  //   },
  // },
  mounted() {
    console.log("Mounted hook is running.");
    const maxRadius = 300;
    let attempts = 350; // 可以根据需要调整
    while (attempts > 0 && this.squares.length > 0) {
      const x = Math.random() * (3 * maxRadius) - maxRadius;
      const y = Math.random() * (3 * maxRadius) - maxRadius;
      if (x * x + y * y <= maxRadius * maxRadius) {
        console.log(attempts);
        const index = Math.floor(Math.random() * this.squares.length);
        this.usedPositions.push({ x, y, color: this.squares[index].color });
        this.squares.splice(index, 1); // 移除已使用的方块
      }
      attempts--;
    }
  },
};
</script>

<style>
.circle-container {
  width: 150px;
  height: 150px;
}

.planet-wrap {
  align-items: center;
  justify-content: center;
  display: flex;
}
</style>
