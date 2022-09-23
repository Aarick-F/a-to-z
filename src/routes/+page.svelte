<script>
  import averSmile from "$lib/assets/aver/AverSmile.png";
  import averPog from "$lib/assets/aver/AverPog.png";
  import averTalk from "$lib/assets/aver/AverTalk.png";
  import averMinkus from "$lib/assets/aver/AverMinkus.png";
  import zefSmile from "$lib/assets/zef/ZefSmile.png";
  import zefPog from "$lib/assets/zef/ZefPog.png";
  import zefTalk from "$lib/assets/zef/ZefTalk.png";
  import zefMinkus from "$lib/assets/zef/ZefMinkus.png";
  const zef = {
    smile: zefSmile,
    talk: zefTalk,
    pog: zefPog,
    minkus: zefMinkus,
  };
  const aver = {
    smile: averSmile,
    talk: averTalk,
    pog: averPog,
    minkus: averMinkus,
  };
  let zefState = "smile";
  let averState = "smile";
  function onKeyDown(e) {
    switch (e.key) {
      case "v":
        zefState = "smile";
        break;
      case "b":
        zefState = "talk";
        break;
      case "n":
        zefState = "pog";
        break;
      case "m":
        zefState = "minkus";
        break;
      case "q":
        averState = "smile";
        break;
      case "w":
        averState = "talk";
        break;
      case "e":
        averState = "pog";
        break;
      case "r":
        averState = "minkus";
        break;
      default:
        break;
    }
  }
</script>

<svelte:head>
  <title>A-to-Z</title>
</svelte:head>
<svelte:window on:keydown|preventDefault={onKeyDown} />

<section>
  <div class="sideline">
    <img
      class="avatar aver {averState === 'pog' ? 'pog-aver' : ''}"
      src={aver[averState]}
      alt="average_atlas's amazing visage"
    />
  </div>
  <div class="feature">
    <div class="presentation">
      <h1>VIDEO HIGHLIGHTS GO HERE</h1>
    </div>
  </div>
  <div class="sideline">
    <img
      class="avatar zef {zefState === 'pog' ? 'pog-zef' : ''}"
      src={zef[zefState]}
      alt="zeflyn's amazing visage"
    />
  </div>
</section>

<style>
  section {
    flex: 1;
    display: flex;
    font-family: Arial, Helvetica, sans-serif;
  }
  .sideline {
    flex: 1;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    /* background: indianred; */
  }
  .feature {
    flex: 2;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 3rem 1rem;
  }
  .presentation {
    width: 100%;
    height: 60vh;
    border: 2px solid #eee;
    border-radius: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #eee;
  }
  .avatar {
    width: 256px;
    margin-bottom: 8rem;
  }
  .aver {
    transform: rotate(-15deg) scaleX(-1);
    animation: float-aver 5s ease-in-out infinite;
  }
  .zef {
    transform: rotate(15deg);
    animation: float-zef 5s ease-in-out infinite;
  }
  .pog-zef {
    animation: pog-zef 0.1s step-end infinite;
  }

  .pog-aver {
    animation: pog-aver 0.1s step-end infinite;
  }

  @keyframes float-aver {
    50% {
      transform: translateY(50px) rotate(-15deg) scaleX(-1);
    }
  }

  @keyframes float-zef {
    50% {
      transform: translateY(50px) rotate(15deg);
    }
  }

  @keyframes pog-zef {
    0% {
      transform: translate(-2px, 2px) rotate(15deg);
    }
    20% {
      transform: translate(1px, -3px) rotate(15deg);
    }
    40% {
      transform: translate(-1px, 0px) rotate(15deg);
    }
    60% {
      transform: translate(3px, -1px) rotate(15deg);
    }
    80% {
      transform: translate(-2px, 0px) rotate(15deg);
    }
    100% {
      transform: translate(0px, 0px) rotate(15deg);
    }
  }
  @keyframes pog-aver {
    0% {
      transform: translate(-2px, 2px) rotate(-15deg) scaleX(-1);
    }
    20% {
      transform: translate(1px, -3px) rotate(-15deg) scaleX(-1);
    }
    40% {
      transform: translate(-1px, 0px) rotate(-15deg) scaleX(-1);
    }
    60% {
      transform: translate(3px, -1px) rotate(-15deg) scaleX(-1);
    }
    80% {
      transform: translate(-2px, 0px) rotate(-15deg) scaleX(-1);
    }
    100% {
      transform: translate(0px, 0px) rotate(-15deg) scaleX(-1);
    }
  }
</style>
