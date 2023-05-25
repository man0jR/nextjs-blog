# Key notes

Next.js aims to have best-in-class developer experience and many built-in features, such as:

- An intuitive page-based routing system (with support for dynamic routes)
- Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
- Automatic code splitting for faster page loads
- Client-side routing with optimized prefetching
- Built-in CSS and Sass support, and support for any CSS-in-JS library
- Development environment with Fast Refresh support
- API routes to build API endpoints with Serverless Functions
- Fully extendable

## Navigation
Routing is built in using the Link component. No external library required. Next.js automatically handles code splitting(download only the required pages and not entire code) and prefetching(load linked pages in the background - only in production) automatically.

## Pre rendering
Static Generation is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request.
Server-side Rendering is the pre-rendering method that generates the HTML on each request.

We can decide which form of pre-rendering is required on per page basis.

### SSG
Export an async function called getStaticProps - which can also fetch data from external api's or DB.
Since this function only runs on server side, DB calls can also be made directly.
SSG runs only one time during build in production and serves the compiled static pages for every request.

### SSR
Export an async function called getServerSideProps. It takes an argument which contains the params in the request
If you need to fetch data at request time instead of at build time, you can try Server-side Rendering.

## Dynamic Routes
For <b>Dynamic Routes</b> under pages directory we can use the file name as `[id].js`. Pages that begin with [ and end with ] are dynamic routes in Next.js.
In SSG, getStaticPaths method will have the param with id of the dynamic path.
In SSR, the dynamic route path can be fetched from context param.