<template>
  <div class="loading">
    <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
      <circle cx="50" cy="50" r="45" />
    </svg>
  </div>
</template>

<style lang="scss" scoped>
@import "~@/styles/base.scss";

.loading {
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    background-color: rgba(255, 255, 255, 0.605);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 12;
  svg {
    animation: 2s linear infinite svg-animation;
    max-width: 50px;
  }
  @keyframes svg-animation {
    0% {
      transform: rotateZ(0deg);
    }
    100% {
      transform: rotateZ(360deg);
    }
  }
  circle {
    animation: 1.4s ease-in-out infinite both circle-animation;
    display: block;
    fill: transparent;
    stroke: $quinto_color;
    stroke-linecap: round;
    stroke-dasharray: 283;
    stroke-dashoffset: 280;
    stroke-width: 10px;
    transform-origin: 50% 50%;
  }
  @keyframes circle-animation {
    0%,
    25% {
      stroke-dashoffset: 280;
      transform: rotate(0);
    }
    50%,
    75% {
      stroke-dashoffset: 75;
      transform: rotate(45deg);
    }
    100% {
      stroke-dashoffset: 280;
      transform: rotate(360deg);
    }
  }
}
</style>
