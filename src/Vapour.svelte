<span style="--i: 1" />
<span style="--i: 3" />
<span style="--i: 16" />
<span style="--i: 5" />
<span style="--i: 13" />
<span style="--i: 20" />
<span style="--i: 6" />
<span style="--i: 7" />
<span style="--i: 10" />
<span style="--i: 8" />
<span style="--i: 17" />
<span style="--i: 11" />
<span style="--i: 12" />
<span style="--i: 14" />
<span style="--i: 2" />
<span style="--i: 9" />
<span style="--i: 15" />
<span style="--i: 4" />
<span style="--i: 19" />

<style>
  span {
    position: relative;
    bottom: 50px;
    display: block;
    margin: 0 2px 50px;
    min-width: 8px;
    height: 120px;
    background: white;
    border-radius: 50%;
    animation: animate 5s linear infinite;
    opacity: 0;
    filter: blur(8px);
    animation-delay: calc(var(--i) * -0.5s);
  }
  @keyframes animate {
    0% {
      transform: translateY(0) scaleX(1);
      opacity: 0;
    }
    15% {
      opacity: 1;
    }
    50% {
      transform: translateY(-150px) scaleX(5);
    }
    95% {
      opacity: 0;
    }
    100% {
      transform: translateY(-300px) scaleX(10);
    }
  }
</style>
