
## Building
As preconditions the following tools must be available:
- cargo (the Rust package manager, used to install mdbook)
- npm (used to manage all javascript dependencies)

Install mdbook and the javascript dependencies:
```
cargo install mdbook
cargo install mdbook-mermaid
npm install
```

Build & open the book:
```
mdbook build --open
```