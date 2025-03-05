### Next.js Interview Questions and Answers

#### 1. What is Next.js?
**Answer:**
Next.js is a React-based framework that enables server-side rendering and static site generation for web applications. It supports features like automatic code splitting, optimized performance, and easy integration with APIs.

#### 2. What are the main features of Next.js?
**Answer:**
- **Server-Side Rendering (SSR)**: Renders pages on the server at request time, improving performance and SEO.
- **Static Site Generation (SSG)**: Generates static HTML at build time, allowing for fast page loads and better SEO.
- **API Routes**: Allows creating API endpoints within the Next.js application.
- **File-Based Routing**: Automatically creates routes based on the file structure in the `pages` directory.
- **Automatic Code Splitting**: Only loads the necessary JavaScript for the page, improving performance.
- **CSS and Sass Support**: Built-in support for CSS and Sass, including CSS Modules and global CSS.

#### 3. What is the difference between Server-Side Rendering (SSR) and Static Site Generation (SSG) in Next.js?
**Answer:**
- **Server-Side Rendering (SSR)**: Pages are rendered on the server at each request. This is useful for dynamic content that changes frequently.
- **Static Site Generation (SSG)**: Pages are generated at build time and served as static files. This is ideal for pages with content that doesn't change often.

#### 4. How do you create a page in Next.js?
**Answer:**
To create a page in Next.js, you need to create a React component in the `pages` directory. The file name determines the route. For example, creating a file `about.js` in the `pages` directory will create a route `/about`.

#### 5. What is file-based routing in Next.js?
**Answer:**
File-based routing in Next.js means that the routing system is based on the file structure in the `pages` directory. Each file in the `pages` directory corresponds to a route in the application.

#### 6. How do you fetch data in Next.js for server-side rendering?
**Answer:**
You can fetch data for server-side rendering using the `getServerSideProps` function. This function runs on the server and fetches data before rendering the page.

```javascript
export async function getServerSideProps(context) {
  // Fetch data from an API
  const res = await fetch(`https://api.example.com/data`);
  const data = await res.json();

  // Pass data to the page via props
  return { props: { data } };
}
```

#### 7. How do you fetch data in Next.js for static site generation?
**Answer:**
You can fetch data for static site generation using the `getStaticProps` function. This function runs at build time and fetches data to generate static pages.

```javascript
export async function getStaticProps() {
  // Fetch data from an API
  const res = await fetch(`https://api.example.com/data`);
  const data = await res.json();

  // Pass data to the page via props
  return { props: { data } };
}
```

#### 8. What is the `getStaticPaths` function used for in Next.js?
**Answer:**
The `getStaticPaths` function is used in dynamic routes to specify which paths should be statically generated at build time. It works together with `getStaticProps` to generate static pages for dynamic routes.

```javascript
export async function getStaticPaths() {
  // Fetch data to determine which paths to generate
  const res = await fetch(`https://api.example.com/paths`);
  const paths = await res.json();

  // Return an array of path objects
  return {
    paths: paths.map(path => ({ params: { id: path.id } })),
    fallback: false
  };
}
```

#### 9. How do you create API routes in Next.js?
**Answer:**
To create API routes in Next.js, you need to create a file in the `pages/api` directory. Each file in this directory corresponds to an API endpoint.

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, world!' });
}
```

#### 10. What is the purpose of the `next.config.js` file in Next.js?
**Answer:**
The `next.config.js` file is used to customize and configure the Next.js application. It allows you to modify the default behavior of Next.js, such as setting environment variables, configuring webpack, and enabling experimental features.

```javascript
// next.config.js
module.exports = {
  env: {
    CUSTOM_API_URL: 'https://api.example.com'
  },
  webpack: (config, { buildId, dev, isServer, defaultLoaders, webpack }) => {
    // Modify webpack config here
    return config;
  }
};
```

#### 11. How do you handle CSS in Next.js?
**Answer:**
Next.js supports CSS and Sass out of the box. You can import CSS files directly in your components or pages. For scoped styles, you can use CSS Modules by naming your files with the `.module.css` or `.module.scss` extension.

```javascript
// Import global CSS in _app.js
import '../styles/globals.css';

// Import CSS Modules in components
import styles from './Button.module.css';

function Button() {
  return <button className={styles.button}>Click me</button>;
}
```

#### 12. How do you enable TypeScript in a Next.js project?
**Answer:**
To enable TypeScript in a Next.js project, create a `tsconfig.json` file in the root directory and install the necessary TypeScript dependencies.

```bash
touch tsconfig.json
npm install --save-dev typescript @types/react @types/node
```

Next.js will automatically detect the `tsconfig.json` file and set up the project to use TypeScript.

#### 13. What are the benefits of using Next.js over Create React App?
**Answer:**
- **Server-Side Rendering**: Next.js supports server-side rendering out of the box, improving performance and SEO.
- **Static Site Generation**: Next.js can generate static sites, providing fast page loads and better SEO.
- **API Routes**: Next.js allows you to create API endpoints within the application.
- **File-Based Routing**: Simplifies routing by using the file structure.
- **Built-In CSS and Sass Support**: Next.js has built-in support for CSS and Sass, including CSS Modules.

#### 14. How do you deploy a Next.js application?
**Answer:**
Next.js applications can be deployed to various platforms, including Vercel, Netlify, AWS, and more. The simplest way is to deploy to Vercel, the company behind Next.js, which provides seamless integration.

```bash
# Install the Vercel CLI
npm install -g vercel

# Deploy the application
vercel
```

#### 15. How do you handle environment variables in Next.js?
**Answer:**
Next.js supports environment variables through the use of `.env` files. You can create a `.env.local`, `.env.development`, or `.env.production` file to define environment-specific variables.

```env
# .env.local
NEXT_PUBLIC_API_URL=https://api.example.com
```

To access the environment variables in your code, use `process.env`.

```javascript
const apiUrl = process.env.NEXT_PUBLIC_API_URL;
```