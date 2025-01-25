0) Init NPM into non-standard location.

`mkdir -p build/js && cd build/js && npm init -y && cd ../..`

1) Install tailwind into non-standard node_modules location (like gradle does)

`npm install --prefix build/js tailwindcss @tailwindcss/cli`

2) Run @tailwindcss/cli

`NODE_PATH=build/js/node_modules npx @tailwindcss/cli -i src/jsMain/resources/input.css -o output.css`

RESULT: the tailwindcss import in input.css fails. Note that tailwind v3 worked with the old style @tailwind imports with these paths.

[https://github.com/tailwindlabs/tailwindcss/issues/15847]
