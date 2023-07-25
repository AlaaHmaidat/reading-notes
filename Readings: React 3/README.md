## React Context:
React Context is a feature in React that allows data to be passed down the component tree without the need to explicitly pass props between each component. It helps in managing state and sharing data between components that are not directly connected in the component hierarchy. Context provides a way to create a global data store that can be accessed by any component within the context's provider. It is particularly useful for passing down data that is required by many components, such as theme information, user authentication state, or language settings.

### useContext Hook:
The useContext is a React Hook that allows functional components to consume data from a React Context. It enables you to access the data stored in the nearest matching Context.Provider component higher up in the tree. The useContext Hook takes the Context object created by React.createContext() as an argument and returns the current value of that Context.

Here's how to use useContext to access data from a React Context within a functional component:

### Step 1: Create a Context:

```
// Create a new Context
import React from 'react';

const MyContext = React.createContext();
export default MyContext;
```

### Step 2: Provide the Context value at the top level of the component tree (usually in the App component):


import React from 'react';
import MyContext from './MyContext';

```
const App = () => {
const sharedData = { message: "Hello from Context!" };

return (
    <MyContext.Provider value={sharedData}>
    {/* Your component tree goes here */}
    </MyContext.Provider>
);
};

export default App;
```

### Step 3: Consume the Context using useContext in a child component:

```
import React, { useContext } from 'react';
import MyContext from './MyContext';

const ChildComponent = () => {
  const dataFromContext = useContext(MyContext);

  return <p>{dataFromContext.message}</p>;
};

export default ChildComponent;
By using useContext, the ChildComponent can access the data passed through the Context without the need for prop drilling.
```

## Next.js:
Next.js is a popular React framework that enhances the development experience by simplifying the setup and introducing powerful features. It provides server-side rendering (SSR) and static site generation (SSG) out of the box, making it easy to build performant, SEO-friendly, and scalable web applications. Next.js also supports features like file-based routing, automatic code splitting, and API routes, which further streamline the development process.
Example of building a scalable web application using Next.js:

Let's consider an example where we want to build a blog website with Next.js. We can use the Next.js framework to create a blog index page that fetches blog posts from an external API and renders them on the server-side.

### Start by setting up a new Next.js project:
```
npx create-next-app my-blog-app
cd my-blog-app

```
### Create a page for the blog index:
### Create a new file named index.js inside the pages directory:
```
// pages/index.js
import React from 'react';

const BlogIndex = ({ posts }) => {
  return (
    <div>
      <h1>Welcome to My Blog</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>
            <h2>{post.title}</h2>
            <p>{post.body}</p>
          </li>
        ))}
      </ul>
    </div>
  );
};

export async function getServerSideProps() {
  // Fetch data from an API (e.g., a blog API)
  const res = await fetch('https://api.example.com/posts');
  const posts = await res.json();

  return {
    props: {
      posts,
    },
  };
}

export default BlogIndex;

```
### Run the Next.js development server:

```
npm run dev
```
Now, when you visit http://localhost:3000, Next.js will render the BlogIndex component on the server-side and fetch blog posts from the API, populating the page with the data.

The use of server-side rendering and static site generation in Next.js allows search engines to index the content properly, leading to better SEO. Additionally, Next.js optimizes the loading and performance of the web application by automatically handling code splitting, so only the necessary JavaScript is loaded for each page. This makes Next.js an excellent choice for building scalable web applications with React.


### *Resources:*
**Reading**

[NextJs](https://nextjs.org/learn/basics/getting-started)

[React Context for Beginners](https://www.freecodecamp.org/news/react-context-for-beginners/)

**Videos**

[Why I’m using Next.js in 2020](https://www.youtube.com/watch?v=rtgbaKBhdkk)

[Learn useContext In 13 Minutes](https://www.youtube.com/watch?v=5LrDIWkK_Bc)


**Bookmark and Review**

[Next.js Examples](https://github.com/vercel/next.js/tree/canary/examples)

## Things I want to know more about