<script>
  import { fly } from "svelte/transition";
  import { cubicInOut } from "svelte/easing";

  export let background = "linear-gradient(to right, #f9f9f9, #e7e7e7)";
</script>

<div
  transition:fly={{ y: 200, easing: cubicInOut, duration: 1000 }}
  class="plate"
  style="background:{background};" />

<style>
  .plate {
    position: absolute;
    bottom: -50px;
    left: 50%;
    transform: translateX(-50%);
    width: 500px;
    height: 200px;
    border-radius: 50%;
    box-shadow: 0 35px 35px rgba(0, 0, 0, 0.2);
  }
  .plate::before {
    content: "";
    position: absolute;
    top: 10px;
    left: 10px;
    right: 10px;
    bottom: 10px;
    border-radius: 50%;
    background: linear-gradient(to left, #f9f9f9, #e7e7e7);
  }
  .plate::after {
    content: "";
    position: absolute;
    top: 30px;
    left: 30px;
    right: 30px;
    bottom: 30px;
    background: radial-gradient(
      rgba(0, 0, 0, 0.2) 25%,
      transparent,
      transparent
    );
    border-radius: 50%;
  }
</style>
