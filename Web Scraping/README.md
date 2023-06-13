# Web Scraping

### What are the key differences between scraping static and dynamic websites?
####  Dynamic websites
A dynamic website is a website that displays different types of content every time a user views it. This display changes depending on a number of factors like viewer demographics, time of day, location, language settings,input, database information, and real-time data

Dynamic websites typically use server-side scripting or programming languages like PHP, Python, Ruby, or JavaScript to generate content on the fly. These scripting languages allow the website to interact with databases, process user input, and generate customized pages for each user request.

One example of a dynamic website is an e-commerce platform like <span style="color:red;">*Amazon*</span>. When you visit Amazon's website, you see a personalized homepage that displays product recommendations based on your browsing history, purchase history, and preferences.

#### Static website
Static web pages are made of fixed code, meaning that the content and layout of the page remain the same unless manually modified by the site developer. Once the static web page is created and deployed, it will display the same information to all users, regardless of their preferences or actions.

static websites like <span style="color:red;">*wikis*</span> are a common example. In the case of a static wiki website, the content is typically created and edited by contributors or administrators using a content management system (CMS) or text editor. Once the content is finalized and saved, it is transformed into static HTML pages.

### Explain at least three techniques or best practices that can be employed to avoid getting blocked while scraping websites.

1. Do not follow the same crawling pattern
Humans generally will not perform repetitive tasks as they browse through a site with random actions. Web scraping bots tend to have the same crawling pattern because they are programmed that way unless specified. Sites that have intelligent anti-crawling mechanisms can easily detect spiders by finding patterns in their actions and can lead to web scraping getting blocked.

2. Make the crawling slower, do not slam the server, treat websites nicely
When scraping websites, it's important to avoid detection by mimicking human behavior. Web scraping bots can be easily detected as they browse faster than humans. To prevent this, add random delays between requests, pause after crawling a few pages, and limit concurrent requests. Keeping a delay of 10-20 seconds between actions is recommended to avoid overloading the website and ensure a respectful scraping process.

3. Use a headless browser like Puppeteer, Selenium or Playwright
These tools allow you to automate web browsers and perform various actions, including rendering JavaScript.

The presence of JavaScript rendering is often used as a simple check to differentiate between bots and humans. Bots typically struggle to execute JavaScript, while most modern web browsers have JavaScript enabled by default. Disabling JavaScript in a browser can severely limit the usability of websites, making it an uncommon scenario for regular users.

### What is Playwright, and how does it assist in web scraping tasks? Provide an example of a use case where Playwright would be particularly beneficial.
Playwright is an automation framework that helps with web scraping tasks by enabling developers to control web browsers and extract data from web pages. It supports multiple browser engines and offers powerful selectors and JavaScript handling capabilities. Playwright is especially beneficial for scraping websites that heavily rely on JavaScript for dynamic content generation. For example, it can be used to scrape data from e-commerce sites with AJAX-based product loading and dynamic rendering.

### Describe the purpose of using Xpath in web scraping, and provide an example of an Xpath expression to select a specific HTML element from a webpage.

Playwright XPath selectors refer to a feature in Playwright that allows developers to specify precise locations of elements on a webpage using XPath expressions. XPath is a language for navigating and selecting elements in XML or HTML documents. With Playwright's XPath selectors, developers can easily target and interact with specific elements on a webpage, such as buttons, input fields, or text elements. This capability enables automation tasks like clicking buttons, filling forms, or extracting data from specific parts of a webpage. Playwright's XPath selectors provide a flexible and powerful way to interact with web elements in an automated manner.

Here's an example of an XPath expression to select a specific HTML element:

Let's say we want to extract the text content of a paragraph (<p>) element with a specific class attribute (class="description") from a webpage. The XPath expression to accomplish this would be:

//p[@class="description"]

### *Resources:*
**Reading**

[Scrape a Dynamic Website with Python](https://scrapingant.com/blog/scrape-dynamic-website-with-python)

[What is Web Scraping?](https://en.wikipedia.org/wiki/Web_scraping)

[How to scrape websites without getting blocked](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)

**Videos**

[Login and Scrape Data with Playwright and Python](https://www.youtube.com/watch?v=H2-5ecFwHHQ&t=60s)

[Python Playwright Tutorial For Beginners](https://www.youtube.com/watch?v=yp1o9biMMWU)

[Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)

[Playwright XPath Selectors](https://www.programsbuzz.com/article/playwright-xpath-selectors)

**Additional Resources**

[Xpath Cheatsheet](https://devhints.io/xpath)

[Render Dynamic Pages - Web Scraping Product Links with Python](https://www.youtube.com/watch?v=MeBU-4Xs2RU)

[Rendering Dynamic Pages 2! - Web Scraping ALL products with Python](https://www.youtube.com/watch?v=B14mtXA7Tyw)

[Selecting an element containing certain text](https://stackoverflow.com/questions/1520429/is-there-a-css-selector-for-elements-containing-certain-text)

## Things I want to know more about








