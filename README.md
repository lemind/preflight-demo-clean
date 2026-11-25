# preflight-demo-clean

> **Controlled test case.** Not a real project: a `package.json` with one dependency, `@solana/kit` 8.6.0 (the
> latest release on 25 Nov 2026), and the lockfile npm resolved for it (`npm install --package-lock-only
> --ignore-scripts`: nothing was installed or run).

It demonstrates the clean case of [dependency-preflight](https://github.com/lemind/dependency-preflight): every
locked version (47, of which 43 are `@solana/*`) is checked against public advisory data, none has an advisory, and
the key package is current, so the verdict is **ready (npm dependencies assessed)** with coverage **complete**.

"Ready" is a statement about known advisories and versions at the time of the run, not a guarantee: a new advisory
or a new `@solana/kit` release can change it on the next run. The check reads lockfiles and manifests only; it is not
a security audit and doesn't read, build, test or run any code.
