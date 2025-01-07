# React Router Dom v6 Nested Route Rerender Bug

This repository demonstrates a subtle bug in React Router Dom v6 related to nested routes and rerenders when navigating between sibling routes.  The issue occurs when navigating from a nested route back to a sibling route at the same nesting level; the sibling component does not always rerender, leading to stale data or UI inconsistencies.

## Bug Description
The bug is demonstrated by the provided `bug.js` file. The application has nested routes, and navigating between sibling routes (e.g., from a nested route within `/about` back to `/home`) may not rerender the `Home` component. This happens even though the URL changes. The `About` component's behavior is similar if you navigate from `/home` nested routes to the `/about` route.

## Solution
The solution is provided in `bugSolution.js`.  Using the `useLocation` hook and a simple effect to force a re-render when the location changes resolves the issue.  This approach ensures all components update appropriately when navigating between routes.

## Setup
1.  Clone this repository.
2.  Run `npm install` to install the dependencies.
3.  Run `npm start` to start the development server.

Then test navigation between the nested routes and observe the issue in `bug.js` and the solution in `bugSolution.js`.