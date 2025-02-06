<template>
    <div class="sidebar">
      <canvas ref="canvas" :height="50" :width="windowWidth"></canvas>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        windowWidth: 0,
      };
    },
    mounted() {
      this.windowWidth = window.innerWidth;
      this.drawRectangle();
      window.addEventListener('resize', this.handleResize);
    },
    beforeUnmount() {
      window.removeEventListener('resize', this.handleResize);
    },
    methods: {
      drawRectangle() {
        const canvas = this.$refs.canvas;
        const ctx = canvas.getContext('2d');
  
        // 绘制灰色矩形
        ctx.fillStyle = 'gray';
        ctx.fillRect(0, 0, this.windowWidth, 50);
  
        // 绘制图标
        this.drawIcons(ctx);
      },
      drawIcons(ctx) {
        const icons = [
          { x: 10, y: 10, width: 30, height: 30, color: 'blue' },
          { x: 50, y: 10, width: 30, height: 30, color: 'red' },
          { x: 90, y: 10, width: 30, height: 30, color: 'green' },
        ];
  
        icons.forEach((icon) => {
          ctx.fillStyle = icon.color;
          ctx.fillRect(icon.x, icon.y, icon.width, icon.height);
        });
      },
      handleResize() {
        this.windowWidth = window.innerWidth;
        this.drawRectangle();
      },
    },
  };
</script>
  
<style>
  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 50px;
    z-index: 1000;
  }
</style>