### Dynamic Routes vs. Static Routes in Next.js

#### Dynamic Routes
In Next.js, dynamic routes allow you to create pages with URLs that depend on external data. This means you can define a single page template and have it render different content based on the parameters in the URL. Dynamic routes are particularly useful for building pages that display data from a database or API. To create a dynamic route in Next.js, you use brackets ([]) to indicate where the dynamic part of the URL should be.

For example, if you have a Next.js application and want to create dynamic pages for different blog posts, you could define a dynamic route as follows:

```javascript
// pages/posts/[slug].js

import { useRouter } from 'next/router';

const Post = () => {
  const router = useRouter();
  const { slug } = router.query;

  return (
    <div>
      <h1>{slug}</h1>
      {/* Fetch and display blog post content based on the 'slug' */}
    </div>
  );
};

export default Post;
```

With this setup, visiting `/posts/first-post` will render the `Post` component with `slug` equal to "first-post."

### Static Routes
On the other hand, static routes are traditional routes where each page is pre-rendered at build time and served as an HTML file to the client. These pages do not depend on external data and are generally ideal for content that doesn't change often. Static routes in Next.js are created by placing components directly inside the `pages` directory. When a static route is accessed, Next.js fetches the pre-rendered HTML file, eliminating the need to generate the page on each request.

### Deploying a Next.js Application
The process of deploying a Next.js application typically involves these key steps:

1. **Production Build**: Create a production build of your Next.js application. This can be done by running the following command in the terminal:

   ```bash
   npm run build
   ```

   ### Deployment Configuration
Configure your application to run in a production environment. Ensure that you have all the necessary environment variables set correctly, such as API keys or database credentials.

### Choose a Deployment Platform
Select a hosting platform for your application. Some popular deployment platforms for Next.js include:

- **Vercel**: Vercel is closely integrated with Next.js and provides an easy deployment process. You can deploy your application directly from your Git repository.

- **Netlify**: Netlify is another popular option that supports static site hosting, which aligns well with Next.js's static site generation capabilities.

- **AWS Amplify**, **Heroku**, and other cloud hosting providers are also viable options.

### Deploy the Application
Depending on your chosen platform, the deployment process may vary. Typically, it involves connecting your hosting account to your Git repository and triggering a deployment from the platform's dashboard.

### Verify and Monitor
After deployment, make sure to verify that your application is working correctly in the production environment. Monitor the application for any errors or performance issues.

### Static File Serving in Next.js
Next.js automatically handles static file serving through the `public` directory. The default folder structure for storing static assets is as follows:

- public
  - images
  - styles
  - js



Files placed in the `public` directory are served directly by the server and are not processed by Webpack. For example, if you have an image named `logo.png` in the `public/images` directory, you can reference it in your Next.js components like this:

```jsx
// components/Header.js

const Header = () => {
  return (
    <header>
      <img src="/images/logo.png" alt="Logo" />
      {/* Rest of the header content */}
    </header>
  );
};

export default Header;
```

Next.js will automatically resolve the correct path to the `logo.png` file during both development and production.

Remember, using the `public` directory is only recommended for truly static files that don't need to be processed or optimized by Next.js. For other assets, like CSS or JavaScript files, it's better to import them directly into your components to take advantage of Next.js's build optimization features.

### *Resources:*
**Reading**

[Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)

[Next.js - Deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)

**Videos**

[Next.js 10 is here](https://www.youtube.com/watch?v=JWCS5IdECVI)


**Bookmark and Review**

[Next.js - Static File Serving](https://nextjs.org/docs/basic-features/static-file-serving)


## Things I want to know more about
