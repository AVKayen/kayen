<script lang="ts">
  import { onMount } from "svelte";
  let moveX = 0;
  let moveY = 0;
  let letter_k =
    "\
KAYEN   ENKAYE \n\
KAYEN  YENKAY  \n\
KAYEN AYENKA   \n\
KAYENKAYENK    \n\
KAYENKAYENK    \n\
KAYENKAYENK    \n\
KAYEN AYENKA   \n\
KAYEN  YENKAY  \n\
KAYEN   ENKAYE ";
  let letter_a =
    "\
    KAYEN      \n\
   NKAYENK     \n\
  ENKAYENKA    \n\
 AENKAYENKAA   \n\
 YENK   KAYE   \n\
AYENKAYENKAYA  \n\
AYENKAYENKAYE  \n\
AYEN     KAYE  \n\
AYEN     KAYE  \n";
  let letter_y =
    "\
 KAYE    NKAY  \n\
  YENK  ENKA   \n\
   ENKAYENK    \n\
    NKAYEN     \n\
     NKAY      \n\
     KAYE      \n\
     KAYE      \n\
     KAYE      \n\
     KAYE      ";
  let letter_e =
    "\
  KAYENKAYENKA \n\
  KAYENKAYENKA \n\
  KAYE         \n\
  KAYENKAYENKA \n\
  KAYENKAYENKA \n\
  KAYE         \n\
  KAYE         \n\
  KAYENKAYENKA \n\
  KAYENKAYENKA ";
  let letter_n =
    "\
  KAYEn   ENKA \n\
  KAYENk  ENKA \n\
  KAYENKK ENKA \n\
  KAYENKKKENKA \n\
  KAYE KAKENKA \n\
  KAYE  AYENKA \n\
  KAYE   YENKA \n\
  KAYE    ENKA \n\
  KAYE    ENKA ";
  let theme = "base";
  let new_k =
    "\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               ";
  let new_a =
    "\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               ";
  let new_y =
    "\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               ";
  let new_e =
    "\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               ";
  let new_n =
    "\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               \n\
               ";

  let randomizeLetter = (i, letterid) => {
    let random = Math.floor(Math.random() * 5);
    switch (letterid) {
      case "k":
        if (random === 0) {
          new_k = new_k.slice(0, i) + "K" + new_k.slice(i + 1);
        } else if (random === 1) {
          new_k = new_k.slice(0, i) + "A" + new_k.slice(i + 1);
        } else if (random === 2) {
          new_k = new_k.slice(0, i) + "Y" + new_k.slice(i + 1);
        } else if (random === 3) {
          new_k = new_k.slice(0, i) + "E" + new_k.slice(i + 1);
        } else if (random === 4) {
          new_k = new_k.slice(0, i) + "N" + new_k.slice(i + 1);
        }
        break;
      case "a":
        if (random === 0) {
          new_a = new_a.slice(0, i) + "K" + new_a.slice(i + 1);
        } else if (random === 1) {
          new_a = new_a.slice(0, i) + "A" + new_a.slice(i + 1);
        } else if (random === 2) {
          new_a = new_a.slice(0, i) + "Y" + new_a.slice(i + 1);
        } else if (random === 3) {
          new_a = new_a.slice(0, i) + "E" + new_a.slice(i + 1);
        } else if (random === 4) {
          new_a = new_a.slice(0, i) + "N" + new_a.slice(i + 1);
        }
        break;
      case "y":
        if (random === 0) {
          new_y = new_y.slice(0, i) + "K" + new_y.slice(i + 1);
        } else if (random === 1) {
          new_y = new_y.slice(0, i) + "A" + new_y.slice(i + 1);
        } else if (random === 2) {
          new_y = new_y.slice(0, i) + "Y" + new_y.slice(i + 1);
        } else if (random === 3) {
          new_y = new_y.slice(0, i) + "E" + new_y.slice(i + 1);
        } else if (random === 4) {
          new_y = new_y.slice(0, i) + "N" + new_y.slice(i + 1);
        }
        break;
      case "e":
        if (random === 0) {
          new_e = new_e.slice(0, i) + "K" + new_e.slice(i + 1);
        } else if (random === 1) {
          new_e = new_e.slice(0, i) + "A" + new_e.slice(i + 1);
        } else if (random === 2) {
          new_e = new_e.slice(0, i) + "Y" + new_e.slice(i + 1);
        } else if (random === 3) {
          new_e = new_e.slice(0, i) + "E" + new_e.slice(i + 1);
        } else if (random === 4) {
          new_e = new_e.slice(0, i) + "N" + new_e.slice(i + 1);
        }
        break;
      case "n":
        if (random === 0) {
          new_n = new_n.slice(0, i) + "K" + new_n.slice(i + 1);
        } else if (random === 1) {
          new_n = new_n.slice(0, i) + "A" + new_n.slice(i + 1);
        } else if (random === 2) {
          new_n = new_n.slice(0, i) + "Y" + new_n.slice(i + 1);
        } else if (random === 3) {
          new_n = new_n.slice(0, i) + "E" + new_n.slice(i + 1);
        } else if (random === 4) {
          new_n = new_n.slice(0, i) + "N" + new_n.slice(i + 1);
        }
        break;
    }
  };
  onMount(() => {
    let i = Math.floor(Math.random() * 140);
    let j = Math.floor(Math.random() * 140);
    let k = Math.floor(Math.random() * 140);
    let l = Math.floor(Math.random() * 140);
    let m = Math.floor(Math.random() * 140);
    setInterval(() => {
      for (let s = 0; s < 10; s++) {
        if (
          letter_k[i] === "K" ||
          letter_k[i] === "A" ||
          letter_k[i] === "Y" ||
          letter_k[i] === "E" ||
          letter_k[i] === "N"
        ) {
          randomizeLetter(i, "k");
        }
        if (
          letter_a[j] === "K" ||
          letter_a[j] === "A" ||
          letter_a[j] === "Y" ||
          letter_a[j] === "E" ||
          letter_a[j] === "N"
        ) {
          randomizeLetter(j, "a");
        }
        if (
          letter_y[k] === "K" ||
          letter_y[k] === "A" ||
          letter_y[k] === "Y" ||
          letter_y[k] === "E" ||
          letter_y[k] === "N"
        ) {
          randomizeLetter(k, "y");
        }
        if (
          letter_e[l] === "K" ||
          letter_e[l] === "A" ||
          letter_e[l] === "Y" ||
          letter_e[l] === "E" ||
          letter_e[l] === "N"
        ) {
          randomizeLetter(l, "e");
        }
        if (
          letter_n[m] === "K" ||
          letter_n[m] === "A" ||
          letter_n[m] === "Y" ||
          letter_n[m] === "E" ||
          letter_n[m] === "N"
        ) {
          randomizeLetter(m, "n");
        }
        i = Math.floor(Math.random() * 142);
        j = Math.floor(Math.random() * 142);
        k = Math.floor(Math.random() * 142);
        l = Math.floor(Math.random() * 142);
        m = Math.floor(Math.random() * 142);
      }
    }, 1);
  });
  let moveBack = () => {
    let interval = setInterval(() => {
      moveX = moveX + (moveX + 1) / 16;
      moveY = moveY + (moveY + 1) / 16;
      if (moveX > 1000) {
        moveX = 1000;
        moveY = 1000;
        clearInterval(interval);
      }
      console.log(moveX);
    }, 1);
  };
  let moveForward = () => {
    let interval = setInterval(() => {
      moveX = moveX - (1000 - moveX + 1) / 16;
      moveY = moveY - (1000 - moveY + 1) / 16;
      if (moveX < 30) {
        moveX = 0;
        moveY = 0;
        clearInterval(interval);
      }
      console.log(moveX);
    }, 1);
  };
</script>

<svelte:head>
  <title>Adam Gałęziewski</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <link rel="stylesheet" href="style.css" />
</svelte:head>

<main style="--mainx: {moveX}px; --mainy: {moveY}px">
  <div id="main-island">
    <h1>Adam Gałęziewski</h1>
    <div class="wierd_text" on:focus>
      <button
        class="letter"
        on:click={() => {
          theme = "k";
        }}>{new_k}</button
      >
      <button
        class="letter"
        on:click={() => {
          theme = "a";
        }}>{new_a}</button
      >
      <button
        class="letter"
        on:click={() => {
          theme = "y";
        }}>{new_y}</button
      >
      <button
        class="letter"
        on:click={() => {
          theme = "e";
        }}>{new_e}</button
      >
      <button
        class="letter"
        on:click={() => {
          theme = "n";
        }}>{new_n}</button
      >
    </div>
    <div class="one-line">
      <p>full stack developer</p>
      <a href="https://github.com/AVKayen">github -></a>
    </div>
    <br />
    <p>things i also do:</p>
    <ul>
      <li>graphic design</li>
      <li>music</li>
      <li>japanese -&gt english &lt-&gt polish translations</li>
      <li>photography</li>
      <li>video</li>
      <li>c++ and rust development</li>
      <li>being a cute catboy ^^</li>
    </ul>
    <button class="goto" on:click={moveBack}>Go to my projects -></button>
  </div>
  <div class="second-island">
    <div class="projects">
      <div class="project">
        <div class="one-line"><h2>kayen.pl</h2><a href="/">go -></a></div>
        <p>
          My personal website. A single page application made with Svelte and hosted on Vercel.
        </p>
      </div>
      <div class="project">
        <div class="one-line"><h2>paste.kayen.pl</h2><a href="https://paste.kayen.pl">go -></a></div>
        <p>
          A pastebin-like website. Private for now.
        </p>
      </div>
      <button class="goto" on:click={moveForward}>&lt- Back</button>
    </div>
  </div>
</main>

{#if theme === "main"}
  <style>
    :root {
      --background-color: #45384a;
      --color-1: #e7a88b;
      --color-2: #edede9;
    }
  </style>
{:else if theme === "k"}
  <style>
    :root {
      --background-color: #343330;
      --color-1: #fbf8e7;
      --color-2: #db5143;
    }
  </style>
{:else if theme === "a"}
  <style>
    :root {
      --background-color: #4e607f;
      --color-1: #feffff;
      --color-2: #cfca36;
    }
  </style>
{:else if theme === "y"}
  <style>
    :root {
      --background-color: #f6f3f6;
      --color-1: #002ecc;
      --color-2: #3359cb;
    }
  </style>
{:else if theme === "e"}
  <style>
    :root {
      --background-color: #2e2d2d;
      --color-1: #f9e38e;
      --color-2: #fe6165;
    }
  </style>
{:else if theme === "n"}
  <style>
    :root {
      --background-color: #c9bfba;
      --color-1: #060604;
      --color-2: #f80d5b;
    }
  </style>
{/if}

<style>
  #main-island {
    transform: translate(var(--mainy), var(--mainx));
  }
  .second-island {
    /* slowly transform second island into view */
    transform: translate(
      calc(var(--mainy) - 1000px),
      calc(var(--mainx) - 1500px)
    );
  }
  .goto {
    background-color: transparent;
    color: var(--color-2);
    border: none;
    border-radius: 5px;
    padding: 10px;
    font-size: 20px;
    font-family: "Fira Code", monospace;
    cursor: pointer;
    transform: translate(0, 0);
  }
  .projects {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
  .project {
    font-family: "Fira Code", monospace;
    margin: 10px;
    width: 80%;
  }
</style>
