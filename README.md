# Matter x Pixi

This repo is a demo of how to integrate Matter JS and PixiJS. Both are excellent libraries for rendering 2D scenes.

- [Matter JS](https://brm.io/matter-js/) - 2D Physics Engine
- [PixiJS](https://www.pixijs.com/) - 2D WebGL renderer that helps in creating rich 2D experiences on the web.

## Why?

Occasionally, you'll want the physics of Matter JS combined with the graphic rendering of PixiJS. Matter JS provides support for basic shapes (rectangles, circles, polygons and svgs) but if you want to add video or imagery to those shapes you'll need to integrate PixiJS.

## How It Works

We use the Matter JS renderer to create basic shapes (bodies). Those shapes abide by Matter's physics and collision rules. We create a PixiJS renderer on top of the Matter world and add Pixi graphics (images, videos, etc) to it. The graphics are the same size and shape as their related Matter body. Using the Pixi ticker we can watch for updates and have the Pixi objects follow the same movement (position and rotation) of their related Matter bodies.

Matter is the invisible world of objects that move based on physics. PixiJS is the world that tracks the Matter object movement with high def graphics.

# Development

Clone this repository and install its dependencies:

```bash
git clone https://github.com/celsowhite/matter-pixi.git
cd matter-pixi
npm install
```

The `public/index.html` file contains a `<script src='bundle.js'>` tag, which means we need to create `public/bundle.js`. The `rollup.config.js` file tells Rollup how to create this bundle, starting with `src/main.js` and including all its dependencies.

`npm run build` builds the application to `public/bundle.js`, along with a sourcemap file for debugging.

`npm start` launches a server, using [serve](https://github.com/zeit/serve). Navigate to [localhost:5000](http://localhost:5000).

`npm run watch` will continually rebuild the application as your source files change.

`npm run dev` will run `npm start` and `npm run watch` in parallel.
