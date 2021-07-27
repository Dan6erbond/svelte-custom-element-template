# Svelte Custom Element Template

This is a project template for [Svelte custom elements](https://svelte.dev/docs#Custom_element_API). It lives at https://github.com/Dan6erbond/svelte-custom-element-template.

To create a new project based on this template, clone this repository:

```bash
git clone https://github.com/Dan6erbond/svelte-custom-element-template.git
```

*Note that you will need to have [Node.js](https://nodejs.org/) and [Yarn](https://yarnpkg.com/) installed on your machine.*

## Get Started

 1. Install dependencies:

```bash
cd svelte-custom-element-template
yarn
```

 2. Run the development server:

```bash
yarn dev
```

 3. Open http://localhost:5000 in your browser. You should see a simple page with a "Hello, world!" message and a counter. Edit a component file in `src` and Rollup's `livereload` plugin will update the page in the browser.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `srv` commands in the [`package.json`](package.json) file to include the option `--host 0.0.0.0` or add the option when running the development server.

## What's Included

 1. Svelte custom elements with reactivity, slots and CSS.
 2. Nested custom elements to showcase shadow DOM and CSS scoping.
 3. Event emitting and event listening in custom elements and [`index.html`](public/index.html).
 4. Using reserved keywords in Svelte `<script>` tags.
 5. Helpful code comments to understand the concepts when building Web Components.

## Scripts

 - `build`: Builds the project for production.
 - `dev`: Runs the development server.
 - `start`: Starts the production server with built files.
 - `check`: Runs the Svelte & Typescript code checker.
 - `lint`: Runs ESLint with the Prettier plugin.
 - `format`: Runs Prettier.

## Building for Production

 1. Run the production build:

```bash
yarn build
```

 2. The built files are in the `dist` folder.
 3. Include the bundle in your HTML:

```html
<!-- index.html -->
<!DOCTYPE html>
<html>
  <head>
    <title>Svelte Custom Element</title>
    <script src="bundle.js"></script>
  </head>
  <body>
    <my-custom-element></my-custom-element>
  </body>
</html>
```

## Using Typescript

This template is already setup with Typescript. Simply add `lang="ts"` to your `<script>` tag to use Typescript or use the `.ts` extension for your Typescript files.

## Contributors

 - [Dan6erbond](https://github.com/Dan6erbond)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
