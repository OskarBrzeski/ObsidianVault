# Installation
Download the Tailwind binary from the official releases: https://github.com/tailwindlabs/tailwindcss/releases.

Then, place the binary either somewhere in your project directory or in one of the directories included in PATH.
# Usage
Refer to the downloaded tailwind binary in the following way:
```bash
tailwindcss -i ./src/input.css -o ./static/styles.css
```
Match the name of the binary and the input and output filepaths to your project structure.
## Inside `input.css`
### Boilerplate
```css
@import "tailwindcss";

@source "../views/**/*.html"
```
### Fonts
```css
@font-face {
	font-family: "FontName";
	src: url("../static/fonts/FontName.ttf");
}

@font-face {
	font-family: "AnotherFont";
	src: url("../static/fonts/AnotherFont.woff2");
}
```
### Themes
https://tailwindcss.com/docs/theme
```css
@theme {
	/* fonts become font-* classes (e.g. font-project-serif) */
	--font-project-serif: "FontName", serif;
	--font-project-sans: "AnotherFont", sans-serif;

	/* colors become color-* classes (e.g. bg-project-primary) */
	--color-project-primary: #123456;
	--color-project-accent: #abcdef;
}
```
### Base layer
Default styling for these elements, can be overridden with other classes later.
```css
@layer base {
	body {
		overflow-x: hidden;
		display: grid;
		grid-template-rows: auto 1fr auto;
		min-height: 100dvh;
	}
	
	h1 {
		@apply text-4xl font-project-sans text-center
	}
}
```
### Components layer
Complex classes for repeated components, can be overridden with other classes later.
```css
@layer components {
	.card {
		@apply flex flex-col w-64 h-80 text-center
	}
}
```