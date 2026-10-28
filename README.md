# Vitest watch mode stops rerunning after a config restart

1. `npm install`
2. `npm test` (starts `vitest --watch`; the test passes)
3. In `vitest.config.mjs`, change `__N__: 0` to `__N__: 1`. Vitest restarts and runs the test.
4. In `src/math.ts`, change `a + b` to `a - b`.

Expected: the test reruns and fails.
Actual: nothing happens. Edits to `tests/math.test.ts` also do not rerun.

Without step 3, step 4 reruns the test every time.
