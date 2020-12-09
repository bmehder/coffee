<script>
  import Controls from "./Controls.svelte";
  import Vapour from "./Vapour.svelte";

  let value = 1;
  const animate = (e) => {
    value = e.detail;
  };
</script>

<Controls on:slide={animate} />

<div class="container">
  <div class="plate" />
  <div class="cup">
    <div class="vapour" style="filter: blur({value}px);">
      <Vapour />
    </div>
    <div class="top">
      <div class="circle">
        <div class="tea" style="top:{value * 2.5}px" />
      </div>
    </div>
    <div class="handle" />
  </div>
</div>

<style>
  :global(*) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  :global(body) {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #607d8b;
  }
  .container {
    position: relative;
    top: 50px;
  }
  .cup {
    position: relative;
    width: 280px;
    height: 300px;
    background: linear-gradient(to right, #f9f9f9, #d9d9d9);
    border-bottom-left-radius: 45%;
    border-bottom-right-radius: 45%;
  }
  .top {
    position: absolute;
    top: -30px;
    left: 0;
    width: 100%;
    height: 60px;
    background: linear-gradient(to right, #f9f9f9, #d9d9d9);
    border-radius: 50%;
  }
  .circle {
    position: relative;
    top: 5px;
    left: 10px;
    width: calc(100% - 20px);
    height: 50px;
    background: linear-gradient(to left, #f9f9f9, #d9d9d9);
    border-radius: 50%;
    overflow: hidden;
  }
  .tea {
    position: absolute;
    top: 0px;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(#c57e65, #323232);
    border-radius: 50%;
  }
  .handle {
    position: absolute;
    top: 40px;
    right: -70px;
    width: 160px;
    height: 180px;
    border: 25px solid #dcdcdc;
    border-left: 25px solid transparent;
    border-bottom: 25px solid transparent;
    border-radius: 50%;
    transform: rotate(42deg);
  }
  .plate {
    position: absolute;
    bottom: -50px;
    left: 50%;
    transform: translateX(-50%);
    width: 500px;
    height: 200px;
    background: linear-gradient(to right, #f9f9f9, #e7e7e7);
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
  .vapour {
    position: relative;
    display: flex;
    z-index: 1;
    padding: 0 20px;
  }
</style>
