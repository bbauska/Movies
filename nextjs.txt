<h2>Automatic Setup</h2>

<p>We recommend creating a new Next.js app using create-next-app, which sets up everything automatically for you. (You don't need to create an empty directory. create-next-app will make one for you.) To create a project, run:</p>

```
npx create-next-app@latest
# or
yarn create next-app
# or
pnpm create next-app
```

<p>If you want to start with a TypeScript project you can use the --typescript flag:</p>

```
npx create-next-app@latest --typescript
# or
yarn create next-app --typescript
# or
pnpm create next-app --typescript
```

<p>After the installation is complete:</p>
<ul>
    <li>Run npm run dev or yarn dev or pnpm dev to start the development server on http://localhost:3000</li>
    <li>Visit http://localhost:3000 to view your application</li>
    <li>Edit pages/index.js and see the updated result in your browser</li>
</ul>

<p>For more information on how to use create-next-app, you can review the create-next-app documentation.</p>

<h2>Manual Setup</h2>

<p>Install next, react and react-dom in your project:</p>

```
npm install next react react-dom
# or
yarn add next react react-dom
# or
pnpm add next react react-dom
```

Open package.json and add the following scripts:

```
"scripts": {
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "lint": "next lint"
}
```

These scripts refer to the different stages of developing an application:

    dev - Runs next dev to start Next.js in development mode
    build - Runs next build to build the application for production usage
    start - Runs next start to start a Next.js production server
    lint - Runs next lint to set up Next.js' built-in ESLint configuration

<p>Create two directories pages and public at the root of your application:</p>
<ol type="1">
<li>pages - Associated with a route based on their file name. For example, pages/about.js is mapped to /about</li>
<li>public - Stores static assets such as images, fonts, etc. Files inside public directory can then be referenced by your code starting from the base URL (/).</li>
</ol>

<p>Next.js is built around the concept of pages. A page is a React Component exported from a .js, .jsx, .ts, or .tsx file in the pages directory. You can even add dynamic route parameters with the filename.</p>

<p>Inside the pages directory, add the index.js file to get started. This is the page that is rendered when the user visits the root of your application.</p>

<p>Populate pages/index.js with the following contents:</p>

```
function HomePage() {
  return <div>Welcome to Next.js!</div>
}

export default HomePage
```

<p>After the set up is complete:</p>
<ul>
<li>Run npm run dev or yarn dev or pnpm dev to start the development server on http://localhost:3000</li>
<li>Visit http://localhost:3000 to view your application</li>
<li>Edit pages/index.js and see the updated result in your browser</li>
</ul>

<p>So far, we get:</p>
<ul>
<li>Automatic compilation and bundling</li>
<li>React Fast Refresh</li>
<li>Static generation and server-side rendering of pages/</li>
<li>Static file serving through public/ which is mapped to the base URL (/)</li>
</ul>

<p>In addition, any Next.js application is ready for production from the start. Read more in our Deployment documentation.</p>
