---
title: Sejarah JavaScript — Dari Netscape ke Mesin Modern
date: 2025-08-21
tags: [javascript, sejarah, web]
---

JavaScript lahir di Netscape pada 1995 ketika Brendan Eich merancang bahasa skrip untuk berjalan di browser hanya dalam waktu sekitar 10 hari. Awalnya disebut Mocha, lalu LiveScript, dan akhirnya JavaScript (sebagian terkait kesepakatan pemasaran di era popularitas Java). Meski awalnya sederhana, JavaScript berevolusi menjadi bahasa pemrograman utama untuk web.

## Tonggak Penting
1. 1995 — Mocha/LiveScript di Netscape Navigator.
2. 1997 — ECMAScript (ES1) distandardisasi oleh ECMA International agar interoperable lintas browser.
3. 2009 — ES5 menghadirkan strict mode, JSON, `Array.prototype` modern; Node.js (V8) membawa JS ke server.
4. 2015 — ES6 (ES2015): `let/const`, arrow function, class, module, Promise, dan banyak fitur inti modern.
5. 2016+ — Rilis tahunan (ES2016, ES2017, …) menambahkan async/await, optional chaining, dan fitur incremental lainnya.

Ekosistem JavaScript juga berkembang: bundler (Webpack, Rollup, esbuild), framework UI (React, Vue, Svelte), dan tool runtime (Node.js, Deno, Bun). Mesin JavaScript seperti V8 (Chrome/Node), SpiderMonkey (Firefox), dan JavaScriptCore (Safari) mempercepat eksekusi via JIT dan optimisasi canggih.

## Contoh Kode Modern

### Dasar: variabel, fungsi, dan template literal
```js
const name = "Philoshi Hacker";
function greet(who) {
  return `Hello, ${who}!`;
}
console.log(greet(name));
```

### Arrow function dan array methods
```js
const nums = [1, 2, 3, 4, 5];
const squaredEven = nums
  .filter(n => n % 2 === 0)
  .map(n => n * n);
console.log(squaredEven); // [4, 16]
```

### Promise dan async/await
```js
function fetchJson(url) {
  return fetch(url).then(r => {
    if (!r.ok) throw new Error(`HTTP ${r.status}`);
    return r.json();
  });
}

async function main() {
  try {
    const data = await fetchJson('https://api.github.com/repos/localan/localan.github.io');
    console.log('Repo:', data.full_name);
  } catch (err) {
    console.error('Error:', err.message);
  }
}

main();
```

### Modul ES (browser modern)
```html
<script type="module">
  import { sum } from './math.js';
  console.log(sum(2, 3));
</script>
```

`math.js`:
```js
export const sum = (a, b) => a + b;
```

## Ringkas
JavaScript berevolusi dari skrip sederhana di browser menjadi platform universal untuk antarmuka pengguna, server, dan alat pengembangan. Siklus rilis tahunan TC39 menjaganya tumbuh stabil, sementara mesin modern membuatnya cepat dan efisien.

