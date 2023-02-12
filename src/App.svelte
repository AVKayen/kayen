<script lang="ts">
  import { onMount } from "svelte";

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
KAYENKAYENKA   \n\
KAYENKAYENKA   \n\
KAYE           \n\
KAYENKAYENKA   \n\
KAYENKAYENKA   \n\
KAYE           \n\
KAYE           \n\
KAYENKAYENKA   \n\
KAYENKAYENKA   ";
  let letter_n =
    "\
KAYEn   ENKA   \n\
KAYENk  ENKA   \n\
KAYENKK ENKA   \n\
KAYENKKKENKA   \n\
KAYE KAKENKA   \n\
KAYE  AYENKA   \n\
KAYE   YENKA   \n\
KAYE    ENKA   \n\
KAYE    ENKA   ";

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
</script>

<main>
  <h1>Adam Gałęziewski</h1>
  <div class="wierd_text" on:focus>
    <div class="letter k">{new_k}</div>
    <div class="letter a">{new_a}</div>
    <div class="letter y">{new_y}</div>
    <div class="letter e">{new_e}</div>
    <div class="letter n">{new_n}</div>
  </div>
  <div class="one-line">
    <p>full stack developer</p>
    <a href="https://github.com/AVKayen">github -></a>
  </div>
  <br>
  <p>things i also do:</p>
  <ul>
    <li>design</li>
    <li>music</li>
    <li>japanese -?> english &lt-&gt polish translations</li>
    <li>photography</li>
    <li>video</li>
    <li>c++ and rust development</li>
    <li>being a cute catboy ^^</li>
  </ul>
</main>

<style>
  .one-line {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-right: 3rem;
  }
  :root {
    overflow: hidden;
    /* coffee color pallete  */
    --color-1: #f2f2f2;
    font-family: JetBrains Mono, system-ui, Avenir, Helvetica, Arial, sans-serif;
    line-height: 1.5;
    font-weight: 400;

    background-color: #45384a;

    font-synthesis: none;
    text-rendering: optimizeLegibility;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    -webkit-text-size-adjust: 100%;
    white-space: pre-line !important;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .wierd_text {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    color: #edede9;
    text-shadow: 0 0 0.2rem #e7a88b;
  }
  .letter {
    text-align: start;
    white-space: pre;
    margin: 1rem;
  }
  p {
    color: #e7a88b;
    font-size: 1.5rem;
    text-shadow: 0 0 0.1rem #e7a88b;
  }
  ul {
    color: #e7a88b;
    font-size: 1.5rem;
    text-shadow: 0 0 0.1rem #e7a88b;
  }
  li {
    color: #e7a88b;
    font-size: 1.5rem;
    text-shadow: 0 0 0.1rem #e7a88b;
  }
  a {
    color: #e7a88b;
    font-size: 1.5rem;
    text-decoration: none;
    text-shadow: 0 0 0.1rem #edede9;
  }
  h1 {
    color: #e7a88b;
    font-size: 3rem;
    text-shadow: 0 0 0.1rem #e7a88b;
  }
</style>
