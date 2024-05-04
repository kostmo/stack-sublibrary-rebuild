# To reproduce the bug

1. Build the executable:
    ```
    stack build bug-repro:exe:bug-repro-exe
    ```
2. Then repeat to ensure all targets are up-to-date.
3. Insert a newline into `src2/Lib2.hs` and save
4. Re-run the above command to build the executable. Observe that files are rebuilt despite that the `lib2` sublibrary is not a dependency of `bug-repro-exe`.

## Equivalent cabal test

1. Build the executable:
    ```
    cabal build bug-repro:exe:bug-repro-exe
    ```
2. Then repeat to ensure all targets are up-to-date.
3. Insert a newline into `src2/Lib2.hs` and save
4. Re-run the above command to build the executable. Observe nothing is rebuilt; only `"Up to date"` is printed.