# NextAuth Session Undefined After Client-Side Navigation in Next.js 13

This repository demonstrates a common issue in Next.js 13 applications using NextAuth.js for authentication.  When navigating to a protected route via client-side navigation (e.g., clicking a link), the session object is undefined, leading to unexpected behavior or errors.  This example provides a reproducible scenario and a solution using the `getServerSideProps` method.

## Problem:

The `About` page attempts to access the session from NextAuth. However, when navigating to `/about` from the `/` page using a client-side `Link`, the `session` is `undefined` because the authentication check happens only on the server-side during the initial load.

## Solution:

The solution employs `getServerSideProps` to fetch the session on the server for each request. This ensures that the `session` is correctly defined, regardless of the navigation method.

## Steps to Reproduce:

1. Clone this repository.
2. Install dependencies using `npm install`.
3. Start the development server using `npm run dev`.
4. Navigate to `/about` from the home page via the provided link.  Observe the issue.
5. Implement the fix (uncomment the solution in `pages/about.js`) and observe the corrected behavior.

## Contributing:

Feel free to contribute to improve this example or provide additional solutions. 