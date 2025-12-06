# Test `pnpm install --ignore-scripts`

If `--ignore-scripts` works, then there should be only two files in `node_modules/dummy-package`. Without `--ignore-scripts`, there is an extra file `POSTINSTALL_WAS_HERE`.
