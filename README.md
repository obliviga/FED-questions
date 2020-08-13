
# Front-End Development Questions


## Have you used CSS workflows like OOCSS or BEM? What do you like and dislike about them?
I've used some aspects of OOCSS. At one of my previous roles, were using an internal CSS framework similar to [Tailwind CSS](https://tailwindcss.com). The purpose of this solution was to write as little CSS as possible via utility classes.

#### Here are some benefits I found using an OOCSS framework:
 - **Page speed** - More custom CSS that's written for each component, the more there is potential for your bundled CSS file to exponentially increase in size. Since OOCSS allows you to write less CSS, your bundled CSS file should be smaller, resulting faster page load.
 - **Coding speed** - When I first experienced a utility-first framework, I have to admit that I was skeptical. I came from a background of writing custom CSS, simply just scoped in a containing class like `.accordionContainer`. However, over time, I've inadvertently memorized most of the util classes and feel like I'm able to style components and layouts way quicker.

#### Here's a major disadvantage of OOCSS in my opinion:
 - **Readability/Debugging** - Sometimes an HTML element has so many util classes, it becomes overwhelming hard to read and debug. For instance: `<input class="bg-white focus:outline-none focus:shadow-outline border border-gray-300 rounded-lg py-2 px-4 block w-full appearance-none leading-normal" />`. If this element was styled with SCSS, many of its styles would appear in one block in the Chrome devtools, and it would be way easier to uncheck and check the styles to help debugging.

When creating carousels with [GlideJS](Glide.js), the markup uses BEM style class names like `glide__arrows`. It's nice writing readable code like this:

    .glide {
	    &__arrows {
		    // styles
		}
	}

## What do you like and dislike about using javascript frameworks for building website frontends?

I think Javascript frameworks make the world go round. If we think about all the apps we may use on a daily basis, they probably use popular frameworks like React, Angular, or Vue. I think writing a large, complex web application like Facebook would be daunting using just vanilla JS. Imagine all of the functions, methods, and utilities you would have to re-invent that frameworks already have established. Unless you're building a web application for the government or some military faction, maybe then I would recommend not using a framework, as you would be able to control every single aspect of the app. Hell, by that logic, you may even consider creating your own programming language and browser!

One disadvantage I think most frameworks bring is a potentially huge learning curve. However, the good thing about choosing to learn a popular open-source framework is the amount of support it has in the development community. If you ever get stuck on an issue, users on Stackoverflow or some other forum would be available to help out.

## How do you serve pages for feature-constrained browsers? What techniques/processes would you use?

There are two popular techniques to serve featured-constrained browsers:
 - **Graceful degredation** - The process of building your UI for the latest and greatest browsers, then writing workarounds or polyfills to account for older browsers that don't support the features that your UI originally has. In this case, your UI "gracefully degrades" when viewed on older browsers.
 - **Progressive enhancement** - The process of building your UI to support older browsers first, then building on top of that code to release features that work on newer browsers.

Personally, I prefer to create my UI to be feature-filled to support the latest browsers first. I use [Babel](https://babeljs.io) in most of my projects, so I'm able to make sure that the UI I have already built works in older browsers. The reason why I prefer graceful degredation is because operating systems like Windows are making an effort to force users to abandon IE11 and use Edge instead.

## Have you worked on projects for blind, low-vision, or mobility-impaired users? What kinds of considerations did you or would you make?

I first learned about the importance of software accessibility at my design internship at IBM in 2015. We were presented with a video outlining what various users with different disabilities have to go through just to navigate the simplest of user interfaces. Ever since then, I've made an extensive effort to make sure that all UI I build is accessible as possible.

Here are some considerations that every UI developer should make in terms of accessibility:

 - Make sure that your entire website can be navigable via keyboard. Many users with disabilities aren't able to use a mouse or trackpad, so it's extremely important that ALL of your interactive UI elements can be cycled through using the Tab key.
 - Make sure that any element with a click handler can also be activated with the Enter key.
 - I recommend using a free screenreader for Google Chrome called [ChromeVox](https://chrome.google.com/webstore/detail/chromevox-classic-extensi/kgejglhpjiefppelpmljglcjbhoiplfn?hl=en). It's developed by Google and works really well in my opinion. Try closing your eyes for the purpose of empathizing with a blind user, then ChromeVox to navigate your website. Doing so may help you find [keyboard traps](https://accessibility.18f.gov/keyboard/) or other stark usability defects.
 - If you're building a website that contains a bunch of navigation UI at the top of the DOM, then you should add an anchor at the top of the DOM that only screenreaders are able to access. This anchor should allow a screenreader user to skip to the main content of the webpage. Otherwise, a screenreader user would have to tab through each navigation item in order to arrive at the main content of the webpage.

## Describe what you like and dislike about CSS preprocessors

Oh man, I can't imagine my career without a CSS preprocessor like SASS. I've been so spoiled with its features like nesting selectors, variables, and mixins. I think the most important feature of SASS is being able to nest selectors. Whenever I look at normal CSS namespacing like this, it makes me cringe:

    .grandparent {
		// styles
	}
	
    .grandparent .parent {
		// styles
	}
	
	.grandparent .parent .child {
		// styles
	}

Of course, there are always some disadvantages with CSS preprocessors like SASS:
 - They have dependencies like NodeJS and Ruby. In order to write CSS and have it appear in the browser, you don't need to install or build anything.
 - There is a learning curve, especially if you're working on a large project and there are methodologies to follow like BEM or OOCSS.

## Have you built any SPAs? What do you like about SPA techniques? What do you like about "traditional" techniques?

I've built a couple of simple SPAs like [Gasatob](https://www.gasatob.com) and [Splitable](https://www.splitable.net). There are a bunch of techniques and technology implemented by many Javascript frameworks like React that help you build SPAs. For example, you can utilize [React Router](https://reactrouter.com) to create a multi-page web app, but it'll perform like a SPA. The URL directory will change, but the page won't need to reload. This technique has been favored and is becoming industry standard, as it creates a much smoother UX with little load times.

## Have you ever worked with retina graphics? What techniques would/did you use? What works and what doesn't about those techniques?





	
