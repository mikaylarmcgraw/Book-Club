# The Road to React (2023 Edition)

## Memoized Functions in React

In this section, we simplified our code by separating the handleFetchStories logic from the useEffect hook and making handleFetchStories a standalone function using React's useCallback hook. The benefits of this approach are:
 - Allows this function to now be reused in the application.
 - By employing the useCallback hook, we prevent the code from getting stuck in an infinite loop. 

useCallback only triggers a re-render when its dependencies, in this case, the searchTerm, change. This ensures that the function is not executed every time the component itself re-renders.