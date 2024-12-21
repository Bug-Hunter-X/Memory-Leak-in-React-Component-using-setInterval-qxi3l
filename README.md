# React setInterval Memory Leak
This example demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to include a cleanup function to clear the interval when the component unmounts. This leads to memory leaks and potential performance issues.

## The Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it fails to clear the interval when the component unmounts, resulting in a continuously running interval even after the component is no longer needed.

## The Solution
The `bugSolution.js` file shows the corrected version, where the `clearInterval` function is used within the cleanup function of the `useEffect` hook. This ensures that the interval is properly cleared when the component unmounts, preventing the memory leak.

## How to Reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install` to install dependencies (if needed).
4. Run the application (instructions might vary depending on your setup).
5. Observe that the `bug.js` version will continue to increment the counter even after removing the component from the view, while the `bugSolution.js` will correctly stop the interval.
