# Svelte + Vite double import error

## The problem

Using `npm run dev`, Vite serves two copies of the same module to the client.

This does not happen when running `npm run build` and serving the created bundle with an http server, for example using `npx http-server -p3000 -c-1 ./dist`.

## This repository

This repository contains an `app` directory with a minimal example based on the template obtained by running `npm init vite@latest test-vite-svelte -- --template svelte`

It also contains `svelte-vite-double-import-lib` which is a minimal library that can cause this behavior.

## How to run

### Development mode showing the weird behavior

- download this repository
- open the `app` directory
- run `npm install`
- run `npm run dev`
- open a browser at http://localhost:3000
- open the javascript console, you should see "module initialized" two times

### Production mode working as expected

- download this repository
- open the `app` directory
- run `npm install`
- run `npm run build`
- run `npx http-server -p3000 -c-1 ./dist`
- open a browser at http://localhost:3000
- open the javascript console, you should see "module initialized" one time
