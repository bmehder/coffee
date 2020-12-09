<script>
  import { fade } from "svelte/transition";
  import Controls from "./Controls.svelte";
  import Vapour from "./Vapour.svelte";
  import Plate from "./Plate.svelte";

  export let message = "It's not a mug. It's a feature.";

  let isPlateShowing = false;
  let isMessageShowing = false;

  let value = 1;
  const animate = (e) => {
    value = e.detail;
  };

  const togglePlate = () => (isPlateShowing = !isPlateShowing);
  const showMessage = () => (isMessageShowing = !isMessageShowing);
</script>

<Controls
  on:slide={animate}
  on:plate={togglePlate}
  on:showmessage={showMessage} />

<div class="container">
  {#if isPlateShowing}
    <Plate />
  {/if}
  <div class="cup">
    <div class="vapour" style="filter: blur({value}px);">
      <Vapour />
    </div>
    {#if isMessageShowing}
      <div transition:fade class="message">
        <p contenteditable>{message}</p>
      </div>
    {/if}
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
    filter: drop-shadow(0 20px 40px #0002);
  }
  .cup {
    position: relative;
    width: 280px;
    height: 300px;
    background: linear-gradient(to right, #f9f9f9, #d9d9d9);
    border-bottom-left-radius: 45%;
    border-bottom-right-radius: 45%;
  }
  .message {
    position: absolute;
    top: 30%;
    left: 50%;
    width: 100%;
    padding: 0 1em;
    transform: translate(-50%);
    text-align: center;
    font-family: cursive;
    font-size: 2em;
    font-weight: bold;
    z-index: 2;
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
  .vapour {
    position: relative;
    display: flex;
    z-index: 1;
    padding: 0 20px;
  }
</style>
