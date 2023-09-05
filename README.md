# tsx-windows-path-error

The issue only occurs on Windows with a directory that includes non-empty brackets `{a}` for example.

To reproduce:

1. Clone this repo
2. `npm ci` to install packages
3. `npm run watch` to start `tsx watch` mode
4. Change a file in the `issues` folder and save the changes
5. Observe the lack of `[tsx] rerunning`

# Observed behaviors:

`./issues/{env}/route.js` fails - brackets are problematic in directories
`./non-issues/{}/file.js` works - the brackets need something between them to cause the failure
`./issues/{/}.js` fails - if you start a bracket in a directory, the issue occurs, and the `/` between directories keeps it from being "empty"
`./issues/{/}/b.js` also fails - ^^
`./non-issues/{works}.js` works - it appears to require the brackets to be started in a directory
