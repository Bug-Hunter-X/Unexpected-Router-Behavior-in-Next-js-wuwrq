# Next.js Router Issue

This repository demonstrates an unexpected behavior when using the `router.push()` method in Next.js.  The issue is that navigating from the about page back to the home page using the code provided will show the home page, however, it will also trigger a new client side render of the home page, resulting in a double render and hence duplicated elements on the page. The code is straightforward; it consists of two pages, Home and About, with links to navigate between them. The unexpected behavior occurs when navigating from About to Home using `router.push('/')`.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm run dev` to start the development server.
4. Navigate to the About page.
5. Click the "Go to Home" button. 
6. Observe that the Home page renders twice, resulting in a duplicated element in the home page.

## Expected Behavior

The expected behavior is that navigating from the About page to the Home page should render the Home page only once.

## Actual Behavior

The actual behavior is that navigating from the About page to the Home page renders the Home page twice, resulting in a duplicated element on the screen, causing the UI to flicker and potentially performance issues.

## Potential Solutions

The provided solution offers a possible fix by using `router.replace()` instead of `router.push()`.