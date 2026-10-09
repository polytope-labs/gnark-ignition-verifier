# Go module proxy for gnark-ignition-verifier

`github.com/consensys/gnark-ignition-verifier` is no longer available on GitHub, and proxy.golang.org does not serve
the version that sp1's `sp1-recursion-gnark-ffi` crate pins (`v0.0.0-20230527014722-10693546ab33`). This branch is a
static Go module proxy for that version. The `main` branch holds the original source history up to the pinned commit.

Add it after the default proxy:

```
GOPROXY=https://proxy.golang.org,https://raw.githubusercontent.com/polytope-labs/gnark-ignition-verifier/goproxy,direct
```

Go checks the downloaded zip against the hash in sp1's `go.sum`
(`h1:z42ewLaLxoTYeQ17arcF4WExZc/eSaN3YVlF7eEaPt4=`), so a modified copy is rejected.
