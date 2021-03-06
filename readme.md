<!---






    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.






-->
# Awesome Universal Rendering [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

Awesome resources about universal rendering. Including:
 - Tools (SSR, SSG, Pre-rendering)
 - Learning Material (SEO benefits, performance benefits, how to implement, etc.)

<br/>

#### Contents

- [Introduction](#introduction)
- [Learning Material](#learning-material)
- [Tools](#tools)

<br/>

## Introduction

Modern view libraries (React, Vue, Angular, etc.) render views to the DOM in the browser but they can as well render views to HTML in Node.js.
This capability can be used to render the same view twice:
First to HTML then again to the DOM. (Re-rendering the view in the browser is called *hydrating*.)
This practice is called *universal rendering* (aka isomorphic rendering).

Universal rendering leads to improvements in SEO, SMO and performance.

There are several techniques to achieve universal rendering:

 - Server-Side Rendering (SSR)
 - Static Site Generators (SSG)
 - Pre-Rendering

In the following we explain these techniques and the benefits of universal rendering.

- [Benefits](#benefits)
- [Techniques](#techniques)

### Benefits

#### SEO

Modern frontends (React, Vue, Angular, ...) use JavaScript to load and display content.
Such JavaScript-generated-content is invisible to crawlers that don't execute JavaScript.
Most crawlers (search engines and social sites) don't execute JavaScript.

The Google crawler is
the only one that can successfully index JavaScript-generated-content.
But it has limitations.
(Mainly around delayed indexing and client-side routing,
see [Learning Material](#learning-material) section.)

If you want your content to be crawled by all other search engines (Bing, Baidu, DuckDuckGo, etc.), then your content needs to be included in your website's HTML.

#### SMO

The crawler of social media sites (Facebook, Twitter, ...) don't execute JavaScript and rely on HTML exclusively.

If you want your website to be correctly previewed when a user shares your website, then the corresponding information needs to be included in your website's HTML.

(SMO means "Social Media Optimization".)

#### Performance

Rendering your website's pages to HTML decreases the perceived loading time:
Once the HTML is loaded, content can already be displayed before any JavaScript is loaded/executed.

The improvement is considerable on mobile
where loading and executing JavaScript is much slower.

### Techniques

Server-Side Rendering (SSR), Pre-Rendering, and Static Site Generators (SSG) are techniques to render JavaScript-generated-content to HTML.
Making the content visible to crawlers and improving performance as well.

There are two ways to render JavaScript-generated-content to HTML:

- **Directly render to HTML**
  <br/>
  Most modern view libraries (React, Vue, Angular, ...) can render views to HTML (instead of rendering to the DOM).
  (E.g. a React component can be rendered to HTML with `require('react-dom/server').renderToStaticMarkup()`.)
- **Render to HTML via headless browser**
  <br/>
  A headless browser runs your website's JavaScript,
  the website's pages are rendered to the DOM of the headless browser,
  and HTML is automatically generated from the resulting DOM.

Leading to the following techniques:

- **Server-Side Rendering (SSR)**
  <br/>
  Directly render your website's pages to HTML at request-time:
  Every time a user requests a page, the server renders the page directly to HTML.
  <br/>
  SSR is the most reliable option if your HTML changes frequently.
  (If your website's content may change after deploy-time,
  e.g. if you website's content is generated by users.)
- **Pre-Rendering**
  <br/>
  A headless browser crawls your website, executes the website's JavaScript, and generates HTML upon the resulting DOM.
  Instead of using a headless browser,
  some pre-renderers directly render your pages to HTML.
- **Static Site Generators (SSG)**
  <br/>
  A static website is a website that doesn't have any server code:
  The website is composed of static browser assets only (HTML, CSS, JavaScript, images, ...).
  Some generators render your views to HTML at build-time:
  When your website is built, each page is rendered to a HTML file that includes all the page's content.
  <br/>
  If your content may only change at deploy-time, then using a SSG is an option.



<br/>
<br/>

## Learning Material

### SEO/SMO & JavaScript

 - [Hacker News Comment](https://news.ycombinator.com/item?id=12759605) - This HN comment explains the problem with SEO and search engines other than Google.
 - [Tweet from Google employee](https://twitter.com/Paul_Kinlan/status/1039852756113080320) - Tweet about delayed Google indexing for pure client-side.
 - [What's Server Side Rendering and do I need it?](https://medium.com/@baphemot/whats-server-side-rendering-and-do-i-need-it-cb42dc059b38) - Good summary about the issues of JavaScript-generated-content.
 - [Deliver search-friendly JavaScript-powered websites (Google I/O '18)](https://www.youtube.com/watch?v=PFwUbgvpdaQ) - Talk that mentions how the Google crawler executes JavaScript. Main take away: Google does index JavaScript-generated-content but with a delay.

### How to implement SSR

 - [The Complete Guide for SSR with Vue](https://ssr.vuejs.org/) - Official guide.
 - [Reactjs SSR Tips and Tricks](https://medium.com/@atahani/reactjs-ssr-tips-and-tricks-be9edff5b7bb)
 - [Server-side rendering with create-react-app, code-splitting, preloaded data, React Router, Helmet, Redux, and Thunk](https://medium.com/@cereallarceny/server-side-rendering-in-create-react-app-with-all-the-goodies-without-ejecting-4c889d7db25e) - Walkthrough of implementing a SSR app based on CRA (without having ejected).

### General discussion

 - [The Benefits of Server Side Rendering Over Client Side Rendering](https://medium.com/walmartlabs/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8)



<br/>
<br/>

## Tools

#### Contents

- [React](#react)
  - [SSR](#ssr)
  - [SSG](#ssg)
  - [Pre-Rendering](#pre-rendering)
- [Vue](#vue)
  - [SSR](#ssr-1)
  - [SSG](#ssg-1)
  - [Pre-Rendering](#pre-rendering-1)
- [Angular](#angular)
  - [SSR](#ssr-2)
  - [Pre-Rendering](#pre-rendering-2)
- [View Library Agnostic](#view-library-agnostic)
  - [SSG](#ssg-2)
  - [Pre-Rendering](#pre-rendering-3)




<br/>

### React

#### SSR

##### Frameworks

 - [Next.js](https://github.com/zeit/next.js#readme)
 - [After.js](https://github.com/jaredpalmer/after.js#readme) - Similar to Next.js but with routing based on React Router.
 - [React Server](https://github.com/redfin/react-server#readme)
 - [Reframe](https://github.com/reframejs/reframe#readme) - A web framework that aims to be truly flexible (no lock-in, everything is ejectable.) It does SSR by default and can be used as SSG.
 - [Fusion.js](https://github.com/fusionjs) - Plugin-based universal web framework maintained by Uber.

##### Libraries

 - [Razzle](https://github.com/jaredpalmer/razzle#readme) - Handles the building. You do the rest.
 - [React Universal Component](https://github.com/faceyspacey/react-universal-component#readme) - Utility to code split your SSR app.
 - [Rogue.js](https://github.com/alidcastano/rogue.js#readme) - SSR utilities focused on flexibility. First-class support for React Router, Apollo GraphQL, Redux, Emotion, and Styled-Components. The build step is up to you (but you can use Razzle.)

##### Boilerplates

 - [cra-ssr](https://github.com/cereallarceny/cra-ssr#readme) - SSR app boilerplate based on CRA (without having ejected).

#### SSG

 - [Gatsby.js](https://github.com/gatsbyjs/gatsby#readme) - SSG based on React and GraphQL.
 - [React Static](https://github.com/nozzle/react-static#readme) - SSG based on React and focused on simplicity.
 - [Phenomic](https://github.com/phenomic/phenomic#readme) - SSG based on a flexible plugin system.
 - [Next.js](https://github.com/zeit/next.js#readme) - Although primarily focused on SSR, Next.js can also generate static sites.
 - [Reframe](https://github.com/reframejs/reframe#readme) - A web framework that aims to be truly flexible (no lock-in, everything is ejectable.) It does SSR by default and can be used as SSG.

#### Pre-Rendering

#### Dynamic Pre-Rendering

Automatically and regularly render your deployed website to HTML.

##### SaaS

 - [Prerender.io](https://prerender.io/)
 - [SEO4Ajax](https://www.seo4ajax.com/)
 - [Prerender.cloud](https://www.prerender.cloud/)
 - [SEO.js](http://getseojs.com/)
 - [BromBone](https://www.brombone.com/)

##### Libraries

 - [Prerender.io Node Server](https://github.com/prerender/prerender#readme) - The prerender.io Node Server is open source.

#### Static Pre-Rendering

 - [Prerender SPA Plugin](https://github.com/chrisvfritz/prerender-spa-plugin#readme) - Uses Puppeteer to crawl & render your pages.
 - [react-snap](https://github.com/stereobooster/react-snap#readme) - Uses Puppeteer to crawl & render your pages.
 - [prep](https://github.com/prismagraphql/prep#readme) - Uses Chromeless to crawl & render your pages.
 - [SSG webpack plugin](https://github.com/markdalgleish/static-site-generator-webpack-plugin#readme) - Directly render your pages to HTML. You provide render functions and routes. All routes are rendered at build-time using the render functions you provided. Also has a crawl mode to use a headless browser to automatically discover your website's URLs.
 - [React Snapshot](https://github.com/geelen/react-snapshot#readme) - Pre-render React apps at build-time. Uses `require('react-dom/server').renderToString` to generate the HTML and uses JSDOM as headless browser to automatically discover your app's URLs.





<br/>

### Vue

#### SSR

##### Frameworks

 - [Nuxt](https://github.com/nuxt/nuxt.js#readme) - Similar to Next.js but for Vue.
 - [Reframe](https://github.com/reframejs/reframe#readme) - A web framework that aims to be truly flexible (no lock-in, everything is ejectable.) It does SSR by default and can be used as SSG.

##### Libraries

 - [vue-server-renderer](https://www.npmjs.com/package/vue-server-renderer) - Official library for SSR with Vue.

#### SSG

 - [Phenomic](https://github.com/phenomic/phenomic#readme) - SSG based on a flexible plugin system.
 - [Reframe](https://github.com/reframejs/reframe#readme) - A web framework that aims to be truly flexible (no lock-in, everything is ejectable.) It does SSR by default and can be used as SSG.

#### Pre-Rendering

#### Dynamic Pre-Rendering

Automatically and regularly render your deployed website to HTML.

##### SaaS

 - [Prerender.io](https://prerender.io/)
 - [SEO4Ajax](https://www.seo4ajax.com/)
 - [Prerender.cloud](https://www.prerender.cloud/)
 - [SEO.js](http://getseojs.com/)
 - [BromBone](https://www.brombone.com/)

##### Libraries

 - [Prerender.io Node Server](https://github.com/prerender/prerender#readme) - The prerender.io Node Server is open source.

#### Static Pre-Rendering

 - [Prerender SPA Plugin](https://github.com/chrisvfritz/prerender-spa-plugin#readme) - Uses Puppeteer to crawl & render your pages.
 - [react-snap](https://github.com/stereobooster/react-snap#readme) - Uses Puppeteer to crawl & render your pages.
 - [prep](https://github.com/prismagraphql/prep#readme) - Uses Chromeless to crawl & render your pages.
 - [SSG webpack plugin](https://github.com/markdalgleish/static-site-generator-webpack-plugin#readme) - Directly render your pages to HTML. You provide render functions and routes. All routes are rendered at build-time using the render functions you provided. Also has a crawl mode to use a headless browser to automatically discover your website's URLs.






<br/>

### Angular

#### SSR

 - [Angular Universal](https://github.com/angular/universal#readme) - Official packages for SSR with Angular.

#### Pre-Rendering

#### Dynamic Pre-Rendering

Automatically and regularly render your deployed website to HTML.

##### SaaS

 - [Prerender.io](https://prerender.io/)
 - [SEO4Ajax](https://www.seo4ajax.com/)
 - [Prerender.cloud](https://www.prerender.cloud/)
 - [SEO.js](http://getseojs.com/)
 - [BromBone](https://www.brombone.com/)

##### Libraries

 - [Prerender.io Node Server](https://github.com/prerender/prerender#readme) - The prerender.io Node Server is open source.

#### Static Pre-Rendering

 - [Prerender SPA Plugin](https://github.com/chrisvfritz/prerender-spa-plugin#readme) - Uses Puppeteer to crawl & render your pages.
 - [react-snap](https://github.com/stereobooster/react-snap#readme) - Uses Puppeteer to crawl & render your pages.
 - [prep](https://github.com/prismagraphql/prep#readme) - Uses Chromeless to crawl & render your pages.
 - [SSG webpack plugin](https://github.com/markdalgleish/static-site-generator-webpack-plugin#readme) - Directly render your pages to HTML. You provide render functions and routes. All routes are rendered at build-time using the render functions you provided. Also has a crawl mode to use a headless browser to automatically discover your website's URLs.




<br/>

### View Library Agnostic

#### SSG

 - [Phenomic](https://github.com/phenomic/phenomic#readme) - SSG based on a flexible plugin system.
 - [Reframe](https://github.com/reframejs/reframe#readme) - A web framework that aims to be truly flexible (no lock-in, everything is ejectable.) It does SSR by default and can be used as SSG.

#### Pre-Rendering

#### Dynamic Pre-Rendering

Automatically and regularly render your deployed website to HTML.

##### SaaS

 - [Prerender.io](https://prerender.io/)
 - [SEO4Ajax](https://www.seo4ajax.com/)
 - [Prerender.cloud](https://www.prerender.cloud/)
 - [SEO.js](http://getseojs.com/)
 - [BromBone](https://www.brombone.com/)

##### Libraries

 - [Prerender.io Node Server](https://github.com/prerender/prerender#readme) - The prerender.io Node Server is open source.

#### Static Pre-Rendering

 - [Prerender SPA Plugin](https://github.com/chrisvfritz/prerender-spa-plugin#readme) - Uses Puppeteer to crawl & render your pages.
 - [react-snap](https://github.com/stereobooster/react-snap#readme) - Uses Puppeteer to crawl & render your pages.
 - [prep](https://github.com/prismagraphql/prep#readme) - Uses Chromeless to crawl & render your pages.
 - [SSG webpack plugin](https://github.com/markdalgleish/static-site-generator-webpack-plugin#readme) - Directly render your pages to HTML. You provide render functions and routes. All routes are rendered at build-time using the render functions you provided. Also has a crawl mode to use a headless browser to automatically discover your website's URLs.


<!---






    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.












    WARNING, READ THIS.
    This is a computed file. Do not edit.
    Edit `/readme.template.md` instead.






-->
