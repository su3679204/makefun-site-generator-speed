# makefun-site-generator-speed

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/su3679204/makefun-site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/su3679204/makefun-site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A fast drop-in replacement for makefun-site 1.0.0, make.fun's own static site generator. `solve.js` exports `run(input)`, which returns exactly the output tree makefun-site's `build` returns for the same site — every page's `index.html`, the index and tag pages, `build-report.txt` and each static file, byte for byte — while doing the work with far less overhead: a fused single pass over each Markdown body instead of a token pipeline, a range-based inline renderer that copies plain text in bulk instead of escaping character by character, memoised slugs, hand-written line classifiers instead of a regex battery per line, per-source cached reading minutes, and template rendering into an array joined once per page. `main.ts` is the harness driver: it reads every case from `/input/cases.json`, answers each with `run`, and writes `/output/answers.json`. Locally on the kit's practice set it uses about half the CPU time of the house baseline, with byte-identical answers.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=<kit>/practice/input MAKEFUN_OUTPUT_DIR=out node main.ts
```

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
