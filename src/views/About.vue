<template>
  <div
    ref="dragCircle"
    class="dragCircle"
    @mounsedown="handleMouseDown"
    @mousemove="handleMouseMove"
    @mouseup="handleMouseUp"
  >
    来拖我呀
  </div>
</template>

<script>
export default {
  data() {
    return {
      relax: 0,
      relaY: 0,
    };
  },
  methods: {
    handleMouseDown(ev) {
      var ev = ev || window.event;

      this.relaX = ev.clientX - this.offsetLeft;
      this.relaY = ev.clientY - this.offsetTop;
    },
    handleMouseMove(ev) {
      var ev = ev || window.event;
      this.$refs.dragCircle.style.left = ev.clientX - this.relaX + "px";
      this.$refs.dragCircle.style.top = ev.clientY - this.relaY + "px";
    },
    handleMouseUp(ev) {
      console.log('up')
    }
  },
};
</script>

<style lang="scss">
.dragCircle {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: #bcbcbc;
  position: absolute;
  text-align: center;
  line-height: 100px;
}
</style>
