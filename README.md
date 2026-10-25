<div align="center">

```
██████╗ ██╗  ██╗██████╗ ██████╗ ███████╗██╗  ██╗███████╗██╗     ██╗
██╔══██╗██║  ██║██╔══██╗╚════██╗██╔════╝██║  ██║██╔════╝██║     ██║
██████╔╝███████║██████╔╝ █████╔╝███████╗███████║█████╗  ██║     ██║
██╔═══╝ ██╔══██║██╔═══╝ ██╔═══╝ ╚════██║██╔══██║██╔══╝  ██║     ██║
██║     ██║  ██║██║     ███████╗███████║██║  ██║███████╗███████╗███████╗
╚═╝     ╚═╝  ╚═╝╚═╝     ╚══════╝╚══════╝╚═╝  ╚═╝╚══════╝╚══════╝╚══════╝
```

### two illustrated deep dives into PHP memory-corruption exploit chains

*deep dive by Aasritha · pixel-art edition · 100% static, 0% actually dangerous*

[![pages](https://img.shields.io/badge/live-github%20pages-2ea44f?style=flat-square)](https://aasritha-y.github.io/php2shell/)
[![type](https://img.shields.io/badge/type-educational-3b7dd8?style=flat-square)](#)

</div>

---

```console
$ ./php2shell --explain
[*] loading walkthroughs ....... done
[*] rendering pixel diagrams ... done
[*] arming payloads ........... skipped (it's just a webpage)
[+] ready. open index.html and enjoy.
```

## what's inside

Two visual, step-by-step walkthroughs of how a deep memory-corruption bug in a PHP engine *could* work — told with pixel-art, color-coded memory blocks, and inline diagrams instead of walls of C.

| chain | the gist |
|---|---|
| **CVE-2026-109618** — the memory-exhaustion chain | starve PHP of memory at the wrong moment, leave a freed block still pointed at, move your data in, let the engine run it |
| **CVE-2026-109619** — the stale global state chain | a fatal error mid-decode leaves a dangling pointer in the worker; the *next* request walks into a cross-request use-after-free |

## see it live

→ **https://aasritha-y.github.io/php2shell/**

Or run it locally — it's just static HTML, no build step:

```console
$ cd php2shell-site
$ python3 -m http.server 8001
# open http://localhost:8001
```

## what's in the box

```
php2shell-site/
├── index.html        # landing page, pick a chain
├── 109618.html       # the memory-exhaustion deep dive
├── 109619.html       # the stale global state deep dive
└── assets/
    └── style.css     # the pixel-art styling
```

<div align="center">

*Educational Purposes Only · © Aasritha*

</div>
