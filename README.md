# tsx-windows-path-error

The issue only occurs on Windows with a directory that includes non-empty brackets `{a}` for example.

To reproduce:

1. Clone this repo
2. `npm ci` to install packages
3. `npm run watch` to start `tsx watch` mode
4. Change `./{env}/route.ts` file
5. Observe the lack of `[tsx] rerunning`
