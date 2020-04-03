# cross-domain-web-app

## Technologies (considering):

- [Django REST Framework](https://www.django-rest-framework.org/)
  - Back-end API with url routing
- [Django CMS](http://docs.django-cms.org/en/latest/)
  - Need the ability to generate content for giving your bookmarks context like why you chose to save a webpage. For the MVC, I imagine this will be a note-taking block.
- [D3.js](https://d3js.org/)
  - This JS library will provide the visualazation features associated with our front-end
- [Vue.js](https://vuejs.org/v2/guide/)
  - Potential front-end framework for our web app. We will be utilizing [Single File Components](https://vuejs.org/v2/guide/single-file-components.html) to create a SPA.
- [React.js](https://reactjs.org/docs/getting-started.html)
  - Another potential front-end framework we will be considering. Utilizes JSX which can be kind of clunky but works well within JS ecosystem.
- [iframes](https://www.dyn-web.com/tutorials/iframes/)
  - We will be investigating iframe elements to render embedded webpages and considering the drawbacks
  - We will explore new technologies that address the issues with iframes such as cross-domain messaging and security

## Notes

### iframes

iframes are used to embed HTML documents within a website.
  - Offer isolated environment unaffected by global JS,CSS
  - Can use most [global event handlers](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers)
  - To send messages between parent and the iframe use `postMessage` function [documented here](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)
  - iframes increase risk of potential vulnerability (utilize `sandbox` and `allow` attributes)
    - See sandbox attributes table on this [guide](https://blog.logrocket.com/the-ultimate-guide-to-iframes/)
    - An empty attribute (i.e. `sandbox=""`) will fully sandbox iframe --> JS cannot be executed + priveleges restricted
  - Do not use iframes excessively without monitoring whats going on --> affect performance --> use lazy loading to load them only when require --> `loading="lazy"`
Responsive iframes (3 options)
    1. Wrap your iframe in an HTML element and add CSS properties --> [article](As more people browse the web using their phones, it is essential to make sure every one of your interfaces is responsive.)
    2. Make iframe responsive by dealing with aspect ratios --> [article](https://css-tricks.com/responsive-iframes/)
    3. Use the [iframe Resizer Library](As more people browse the web using their phones, it is essential to make sure every one of your interfaces is responsive.)
    - TODO: Need to investigate the pros and cons of each approach
[Negative features of iframes (relevant)](https://medium.com/@bluepnume/iframes-are-just-terrible-heres-how-they-could-be-better-974b731f0fb4)
  - Communication is tricky: messages are fire-and-forget with not error handling or responses (can't pass interesting data types)
  - Problematic security
  
Potential Alternatives
  - [Zoid](https://medium.com/@bluepnume/introducing-xcomponent-seamless-cross-domain-web-components-from-paypal-c0144f3e82bf)
    - Used by PayPal because one of its main value-props is security.
  - [Post-Robot](https://medium.com/@bluepnume/introducing-post-robot-smart-cross-domain-messaging-from-paypal-bebf27c8619e)
  - [Lecture on Cross-Domain Web Components](https://vimeo.com/180426382)
    - Integrate really well with React because of props that communicate with data-down/actions-up (bidirectional)
    - Encapsulation of components


## Setup Phase:
