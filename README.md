# Test `pnpm install --ignore-scripts`

If `--ignore-scripts` works, then the output should be like:

```
$ pnpm install --no-lockfile --ignore-scripts
(node:2746623) [DEP0169] DeprecationWarning: `url.parse()` behavior is not standardized and prone to
errors that have security implications. Use the WHATWG URL API instead. CVEs are not issued for `url.
parse()` vulnerabilities.
(Use `node --trace-deprecation ...` to show where the warning was created)
Packages: +1
+
Progress: resolved 1, reused 1, downloaded 0, added 1, done

dependencies:
+ dummy-package 0.0.0

Done in 277ms using pnpm v9.15.9
```

Without `--ignore-scripts`, the output is like:

```
$ pnpm install --no-lockfile
(node:2745423) [DEP0169] DeprecationWarning: `url.parse()` behavior is not standardized and prone to
errors that have security implications. Use the WHATWG URL API instead. CVEs are not issued for `url.
parse()` vulnerabilities.
(Use `node --trace-deprecation ...` to show where the warning was created)
Packages: +1
+
Progress: resolved 1, reused 1, downloaded 0, added 1, done
node_modules/.pnpm/dummy-package@file+..+dummy-package/node_modules/dummy-package: Running postinstal
node_modules/.pnpm/dummy-package@file+..+dummy-package/node_modules/dummy-package: Running postinstal
l script, done in 7ms

dependencies:
+ dummy-package 0.0.0

Done in 290ms using pnpm v9.15.9
```
