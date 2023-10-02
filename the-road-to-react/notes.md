# The Road to React (2023 Edition)

## Memoized Functions in React

In this section, we simplified our code by separating the `handleFetchStories` logic from the `useEffect` hook and making `handleFetchStories` a standalone function using React's `useCallback` hook. The benefits of this approach are:
 - Allows this function to now be reused in the application.
 - By employing the `useCallback` hook, we prevent the code from getting stuck in an infinite loop. 

`useCallback` only triggers a re-render when its dependencies, in this case, the `searchTerm`, change. This ensures that the function is not executed every time the component itself re-renders.

## Explicit Data Fetching with React

To avoid rate limits and errors, we modified the API fetching process for stories. We switched from implicit fetching (to search on `searchTerm` change) to explicit fetching by introducing a submit button in the code. When the user clicks this button, the onClick event handler uses the stateful value of the `url`, which is only set when the user interacts with the button. The `url` includes the `searchTerm`` appended to the API route when a user submits.

## Third party libraries in react

This section explains how to enhance compatibility with older browsers and testing environments by substituting the fetch API with a third-party library like Axios. It subsequently guides you on installing the third-party library and making any necessary code adjustments.

## Async/Await in React

In this section, we'll explore replacing the "then/catch" syntax with "async/await." One advantage of adopting the "async/await" approach is that it makes the code appear synchronous. Actions following the "await" keyword are only executed once the promise is resolved. You can still enclose the "async/await" function in a "try/catch" block for error handling, but many find "async/await" to be more readable, depending on the team's preference.

## Forms in React

In this section we enclose our search input field and submit button in an HTML form element. We make the following adjustments:

- We move the handleSearchSubmit() function from the button's onClick attribute to the form's onSubmit attribute.
- We use preventDefault() to stop the default behavior of the HTML form, which would normally reload the browser on submission.
- By transferring handleSearchSubmit() to the form's onSubmit attribute, we enable the form to be submitted when the "Enter" key is pressed.