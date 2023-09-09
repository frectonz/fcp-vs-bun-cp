# `fcp` vs `bun cp`

If you have nix installed, this command will install `bun`, `fcp` and `hyperfine`.

```bash
nix develop
```

The test command is this. Don't forget to have a large file in `/tmp/huge`.

```bash
hyperfine "fcp /tmp/huge /tmp/dest" "bun ./cp-r.mjs /tmp/huge /tmp/dest" --prepare="rm -rf /tmp/dest" --warmup=20
```

