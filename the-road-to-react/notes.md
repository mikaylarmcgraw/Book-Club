# The Road to React (2023 Edition)

## Memoized Functions in React

In this section, we simplified our code by separating the `handleFetchStories` logic from the `useEffect` hook and making `handleFetchStories` a standalone function using React's `useCallback` hook. The benefits of this approach are:
 - Allows this function to now be reused in the application.
 - By employing the `useCallback` hook, we prevent the code from getting stuck in an infinite loop. 

`useCallback` only triggers a re-render when its dependencies, in this case, the `searchTerm`, change. This ensures that the function is not executed every time the component itself re-renders.

## Explicit Data Fetching with React

To avoid rate limits and errors, we modified the API fetching process for stories. We switched from implicit fetching (to search on `searchTerm` change) to explicit fetching by introducing a submit button in the code. When the user clicks this button, the onClick event handler uses the stateful value of the `url`, which is only set when the user interacts with the button. The `url` includes the `searchTerm`` appended to the API route when a user submits.