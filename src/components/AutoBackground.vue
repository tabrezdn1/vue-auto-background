<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "AutoBackground",
  props: {
    refresh: {
      type: Number,
      default: 1000,
    },
    auto: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      refreshRate: null,
    };
  },
  mounted() {
    this.initData();

    this.initAuto();
  },
  methods: {
    initData() {
      if (this.$props.refresh) {
        this.refreshRate = this.refresh;
      }
    },
    initAuto() {
      if (this.$props.auto) {
        setInterval(this.updateBackground, this.refreshRate);
      }
    },
    updateBackground() {
      document.body.style.background = this.getRandomColour();
    },
    getRandomColour() {
      return `hsl(${Math.floor(Math.random() * 360)}, 100%, 50%)`;
    },
  },
};
</script>
