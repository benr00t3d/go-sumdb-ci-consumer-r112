# Reporter-owned SumDB CI consumer

This repository is a bounded, reporter-owned consumer for validating the
execution consequence of a Google-signed cross-key SumDB record. It imports
only the reporter-owned
`github.com/benr00t3d/go-byteman-crosswrite-canary@v0.0.8` package.

The one-shot workflow uses stock Go with `GOSUMDB=sum.golang.org` and a
fail-closed reporter-owned GOPROXY. Success requires the downloaded package to
compile and create a fixed marker in `/tmp/r112-proof-ci`. The workflow has
read-only repository permissions and uploads only the marker receipt.
