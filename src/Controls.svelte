<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  let value = 1;
</script>

<div class="controls">
  <label for="drink"> Drink: </label>
  <input
    name="drink"
    type="range"
    on:input={() => dispatch('slide', value)}
    bind:value
    min="1"
    max="20" />
  <div class="btn-group">
    <button on:click={() => dispatch('plate')}>Use Plate</button>
    <button on:click={() => dispatch('showmessage')}>Show Message</button>
  </div>
</div>

<style>
  .controls {
    position: absolute;
    top: 20px;
    left: 20px;
  }
  .controls label {
    color: white;
    font-size: 1.2em;
    font-weight: 600;
  }
  input[type="range"] {
    -webkit-appearance: none;
    margin: 10px 0;
    width: 100%;
    background: transparent;
    border: none;
  }
  input[type="range"]:focus {
    outline: none;
  }
  input[type="range"]::-webkit-slider-runnable-track {
    width: 100%;
    height: 10px;
    cursor: pointer;
    animate: 0.2s;
    box-shadow: 1px 1px 1px #000000;
    background: #c57e65;
    border-radius: 5px;
    border: 1px solid #000000;
  }
  input[type="range"]::-webkit-slider-thumb {
    box-shadow: 1px 1px 1px #000000;
    border: 1px solid #000000;
    height: 28px;
    width: 28px;
    border-radius: 4px;
    background: darkorange;
    cursor: pointer;
    -webkit-appearance: none;
    margin-top: -10px;
  }
  input[type="range"]:focus::-webkit-slider-runnable-track {
    background: #c57e65;
  }
  input[type="range"]::-moz-range-track {
    width: 100%;
    height: 10px;
    cursor: pointer;
    animate: 0.2s;
    box-shadow: 1px 1px 1px #000000;
    background: #c57e65;
    border-radius: 5px;
    border: 1px solid #000000;
  }
  input[type="range"]::-moz-range-thumb {
    box-shadow: 1px 1px 1px #000000;
    border: 1px solid #000000;
    height: 28px;
    width: 28px;
    border-radius: 4px;
    background: darkorange;
    cursor: pointer;
  }
  input[type="range"]::-ms-track {
    width: 100%;
    height: 10px;
    cursor: pointer;
    animate: 0.2s;
    background: transparent;
    border-color: transparent;
    color: transparent;
  }
  input[type="range"]::-ms-fill-lower {
    background: #c57e65;
    border: 1px solid #000000;
    border-radius: 10px;
    box-shadow: 1px 1px 1px #000000;
  }
  input[type="range"]::-ms-fill-upper {
    background: #c57e65;
    border: 1px solid #000000;
    border-radius: 10px;
    box-shadow: 1px 1px 1px #000000;
  }
  input[type="range"]::-ms-thumb {
    box-shadow: 1px 1px 1px #000000;
    border: 1px solid #000000;
    height: 28px;
    width: 28px;
    border-radius: 4px;
    background: darkorange;
    cursor: pointer;
  }
  input[type="range"]:focus::-ms-fill-lower {
    background: #c57e65;
  }
  input[type="range"]:focus::-ms-fill-upper {
    background: #c57e65;
  }
  .btn-group {
    display: flex;
    flex-direction: column;
    justify-content: start;
  }
  button {
    padding: 0.5em 1em;
    background: darkorange;
    border: none;
    outline: none;
    border-radius: 4px;
    color: white;
    font-size: 1.2em;
    font-weight: 600;
  }
</style>
