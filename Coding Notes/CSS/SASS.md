SASS is a superset of CSS. It can be used to write stylesheets using a more convenient syntax and compile them to regular CSS.
# Install
```bash
npm install -D sass
```
# Use
Compile whenever changes occur in `.scss` files;
```bash
npx sass --watch input.scss output.css  # individual file
npx sass --watch src/sass:src/css  # all files in src/sass
```
