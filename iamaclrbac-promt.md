30 direct, high-impact suggestions to prompt your AI to optimize your massive school app:

Core Architecture & Loading
Lazy Load Routes: Have the AI wrap all major user-role dashboards (Admin, Teacher, Student) in React.lazy() and Suspense.

Role-Based Chunking: Instruct the AI to separate component imports so Student code never loads in the Admin's browser session.

Implement React Query: Use TanStack Query for all API calls to enable automatic caching and background data synchronization.

Skeleton Screens: Generate "Skeleton" components to show while data is fetching, making the app feel faster to the user.

Virtualize Long Lists: Use react-window for huge lists like student directories or gradebooks to only render visible rows.

Memoize RBAC Checks: Wrap Role-Based Access logic in useMemo so it doesn't recalculate on every minor state update.

Global State Management: Use Zustand instead of Redux; it’s lighter and easier for the AI to implement without boilerplate.

Atomic Components: Break the UI into small, reusable atoms to prevent one large component from re-rendering the whole page.

Data & API Optimization
Pagination by Default: Ensure every "List" view (users, books, grades) uses limit/offset or cursor-based pagination.

Debounce Search Inputs: Add a 300ms debounce to all search bars (e.g., searching for a student) to stop excessive API hits.

Prefetching: Tell the AI to "prefetch" the Teacher dashboard data when the user hovers over the login button.

Optimistic Updates: When a teacher enters a grade, update the UI immediately before the server confirms the save.

Batch API Requests: Combine multiple small requests (like User Profile + School Settings) into a single "Initial Load" API call.

Error Boundaries: Wrap each major tool in an Error Boundary so one failing module doesn't crash the entire school app.

UI & Asset Handling
Tree-Shakable Icons: Use lucide-react or heroicons and ensure only specific icons are imported, not the whole library.

Tailwind JIT: Ensure the AI uses standard Tailwind classes so the CSS bundle stays tiny during the build process.

Image Compression: Implement a utility to handle profile pictures using WebP format and lazy loading attributes.

Conditional Rendering: Don't just hide unauthorized tools with CSS; use logic to ensure their code never enters the DOM.

Form Optimization: Use react-hook-form to prevent the entire page from re-rendering every time a user types in a field.

Avoid Inline Functions: Instruct the AI to define functions outside of the return statement to prevent unnecessary re-renders.

App Scalability & Logic
Context Per Module: Instead of one giant "App Context," create smaller contexts for "Academic," "Finance," and "Communication."

Web Workers: For heavy calculations (like generating report card PDFs), offload the logic to a Web Worker.

Local Storage Caching: Store static data like "Class List" or "Subject Codes" in localStorage to survive page refreshes.

Throttle Scroll Events: If you have parallax or scroll-based animations, use a throttle to save CPU cycles.

Zod Validation: Use Zod for schema validation to catch data errors early before they reach the complex UI components.

Preload Critical Fonts: Add link tags to the HTML head to load your main font early, preventing "Layout Shift."

Avoid Nested State: Keep your data flat (denormalized) so updating one student's grade doesn't trigger a re-render of the whole class.

Clean Up Effects: Ensure every useEffect has a cleanup function to prevent memory leaks in a long-running app.

Dynamic Modals: Don't render every "Edit User" modal at once; render them only when the specific "Edit" button is clicked.

Production Build Settings: Since you are on Android, ask the AI to provide a vite.config.js or webpack config optimized for "Terser" minification.