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

![frectonz-1](./frectonz-1.jpg)
![frectonz-2](./frectonz-2.jpg)
![alex-1](./alex-1.jpg)
![yohannestz-1](./yohannestz-1.jpg)
