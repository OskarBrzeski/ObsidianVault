React Router DOM allows you to directly link to a react component via the page URL.
# Install
```bash
npm install react-router-dom
```
# Use
In `src/main.jsx` or `src/main.tsx`:
```tsx
import { StrictMode } from "react"
import { createRoot } from "react-dom/client"
import { BrowserRouter } from "react-router-dom"
import App from "./App.tsx"  // App.jsx if not using typescript
import "./index.css"

createRoot(document.getElementById("root")!).render(  // ! only for typescript
    <StrictMode>
	    <BrowserRouter>
		    <App />
		</BrowserRouter>
	</StrictMode>
)
```
In `src/App.jsx` or `src/App.tsx`:
```tsx
import {Route, Routes} from "react-router-dom"
import HomePage from "./pages/HomePage"
import UserPage from "./pages/UserPage"
import "./App.css"

function App() {
	return <main>
		<Routes>
			<Route path="/" element={<HomePage />} />
			<Route path="/user" element={<UserPage />} />
		</Routes>
	</main>
}
```
You can turn any component into a link:
```tsx
<Link to="/user">
	Click here to see the user page
</Link>

<Link to="/user">
	<UserProfilePicture />
</Link>
```