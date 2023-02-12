<script type="module">

import { onMount } from "svelte";


let letter_k = "\
KAYEN   ENKAYE \n\
KAYEN  YENKAY  \n\
KAYEN AYENKA   \n\
KAYENKAYENK    \n\
KAYENKAYENK    \n\
KAYENKAYENK    \n\
KAYEN AYENKA   \n\
KAYEN  YENKAY  \n\
KAYEN   ENKAYE ";
let letter_a = "\
  KAYEN      \n\
 NKAYENK     \n\
ENKAYENKa    \n\
aENKAYENKA    \n\
YENK  NKAYE   \n\
aYENkayeNKAYe  \n\
AYENKAYENKAYE  \n\
AYEN     KAYE  \n\
AYEN     KAYE  \n";
let letter_y = "\
KAYE    NKAY  \n\
YENK  ENKA   \n\
 ENKAYENK    \n\
  NKAYEN     \n\
   NKAY      \n\
   KAYE      \n\
   KAYE      \n\
   KAYE      \n\
   KAYE      ";
let letter_e = "\
KAYENKAYENKA   \n\
KAYENKAYENKA   \n\
KAYE           \n\
KAYENKAYENKA   \n\
KAYENKAYENKA   \n\
KAYE           \n\
KAYE           \n\
KAYENKAYENKA   \n\
KAYENKAYENKA   ";
let letter_n = "\
KAYEn   ENKA   \n\
KAYEN   ENKA   \n\
KAYENk  ENKA   \n\
KAYENKa ENKA   \n\
KAYENKAyENKA   \n\
KAYENKAYENKA   \n\
KAYEN AYENKA   \n\
KAYEN  YENKA   \n\
KAYEN   ENKA   ";

export let new_k = "\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             ";
             export let new_a = "\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             ";
             export let new_y = "\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             ";
             export let new_e = "\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             \n\
             ";
             export let new_n = "\
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
}

onMount(() => {
let i = Math.floor(Math.random() * 140);
let j = Math.floor(Math.random() * 120);
let k = Math.floor(Math.random() * 140);
let l = Math.floor(Math.random() * 140);
let m = Math.floor(Math.random() * 140);
let interval = setInterval(() => {
  if (letter_k[i] === "K" || letter_k[i] === "A" || letter_k[i] === "Y" || letter_k[i] === "E" || letter_k[i] === "N") {
    randomizeLetter(i, 'k');
  }
  if (letter_a[j] === "K" || letter_a[j] === "A" || letter_a[j] === "Y" || letter_a[j] === "E" || letter_a[j] === "N") {
    randomizeLetter(j, 'a');
  }
  if (letter_y[k] === "K" || letter_y[k] === "A" || letter_y[k] === "Y" || letter_y[k] === "E" || letter_y[k] === "N") {
    randomizeLetter(k, 'y');
  }
  if (letter_e[l] === "K" || letter_e[l] === "A" || letter_e[l] === "Y" || letter_e[l] === "E" || letter_e[l] === "N") {
    randomizeLetter(l, 'e');
  }
  if (letter_n[m] === "K" || letter_n[m] === "A" || letter_n[m] === "Y" || letter_n[m] === "E" || letter_n[m] === "N") {
    randomizeLetter(m, 'n');
  }
  i = Math.floor(Math.random() * 140);
  j = Math.floor(Math.random() * 140);
  k = Math.floor(Math.random() * 140);
  l = Math.floor(Math.random() * 140);
  m = Math.floor(Math.random() * 140);
}, 0.001);
});

</script>