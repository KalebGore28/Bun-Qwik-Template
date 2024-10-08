# Containerized Bun-Qwik Stack

-   **Development Environment**: This project includes a dev container configuration that automatically sets up a ready-to-go development environment using Visual Studio Code.

    > **Note:** You may need to kill the terminal and reopen it in Visual Studio Code.

-   **Production Container**: Provides a [command](#Docker) and Dockerfile to containerize the entire project into a production-ready Docker container.
-   **Dependencies**:
    -   Docker
    -   Visual Studio Code
    -   [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension from the VS Code Marketplace

    > **Updating Bun:** If you need to update bun, just rebuild the container.

# Qwik City App ⚡️

-   [Qwik Docs](https://qwik.dev/)
-   [Discord](https://qwik.dev/chat)
-   [Qwik GitHub](https://github.com/QwikDev/qwik)
-   [@QwikDev](https://twitter.com/QwikDev)
-   [Vite](https://vitejs.dev/)

---

## Project Structure

This project is using Qwik with [QwikCity](https://qwik.dev/qwikcity/overview/). QwikCity is just an extra set of tools on top of Qwik to make it easier to build a full site, including directory-based routing, layouts, and more.

Inside your project, you'll see the following directory structure:

```
├── public/
│   └── ...
└── src/
    ├── components/
    │   └── ...
    └── routes/
        └── ...
```

-   `src/routes`: Provides the directory-based routing, which can include a hierarchy of `layout.tsx` layout files, and an `index.tsx` file as the page. Additionally, `index.ts` files are endpoints. Please see the [routing docs](https://qwik.dev/qwikcity/routing/overview/) for more info.

-   `src/components`: Recommended directory for components.

-   `public`: Any static assets, like images, can be placed in the public directory. Please see the [Vite public directory](https://vitejs.dev/guide/assets.html#the-public-directory) for more info.

## Add Integrations and deployment

Use the `bun qwik add` command to add additional integrations. Some examples of integrations includes: Cloudflare, Netlify or Express Server, and the [Static Site Generator (SSG)](https://qwik.dev/qwikcity/guides/static-site-generation/).

```shell
bun run qwik add # or `bun qwik add`
```

## Development

Development mode uses [Vite's development server](https://vitejs.dev/). The `dev` command will server-side render (SSR) the output during development.

```shell
bun run dev # or `bun dev`
```

> Note: during dev mode, Vite may request a significant number of `.js` files. This does not represent a Qwik production build.

## Preview

The preview command will create a production build of the client modules, a production build of `src/entry.preview.tsx`, and run a local server. The preview server is only for convenience to preview a production build locally and should not be used as a production server.

```shell
bun run preview # or `bun preview`
```

## Production

The production build will generate client and server modules by running both client and server build commands. The build command will use Typescript to run a type check on the source code.

```shell
bun run build # or `bun build`
```

## Docker

The docker build will create a containerized production ready version of you app.

```shell
bun run docker # or `bun docker`
```

## Bun Server

This app has a minimal [Bun server](https://bun.sh/docs/api/http) implementation. After running a full build, you can preview the build using the command:

```shell
bun run serve # or `bun serve`
```

Then visit [http://localhost:3000/](http://localhost:3000/)
