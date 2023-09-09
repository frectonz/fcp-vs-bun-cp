# `fcp` vs `bun cp`

If you have nix installed, this command will install `bun`, `fcp` and `hyperfine`.

```bash
nix develop
```

The test command is this. Don't forget to have a large file in `/tmp/huge`.

```bash
hyperfine "fcp /tmp/huge /tmp/dest" "bun ./cp-r.mjs /tmp/huge /tmp/dest" --prepare="rm -rf /tmp/dest" --warmup=20
```

# Context

This repo was created to test [Jarred Sumner's](https://twitter.com/jarredsumner/status/1697106543920271524) (creator of bun) claim that bun's `cp` implementation is faster than the rust based `fcp` in this [tweet](https://twitter.com/jarredsumner/status/1697106543920271524).

# Sample Runs

`bun` `1.04x` faster than `fcp`

![frectonz-1](./runs/frectonz-1.jpg)

----
`fcp` `1.19x` faster than `bun`

![frectonz-2](./runs/frectonz-2.jpg)

---
`fcp` `1.02x` faster than `bun`

![alex-1](./runs/alex-1.jpg)

---
`bun` `1.20x` faster than `fcp`

![alex-2](./runs/alex-2.jpg)

---
`fcp` `1.09x` faster than `bun`

![yohannestz-1](./runs/yohannestz-1.jpg)

---
`fcp` `1.04x` faster than `bun`

![dgcp3-1](./runs/dgcp3-1.jpg)
