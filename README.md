# Arcbook

An opinionated variation of the [arc42 Template](https://www.arc42.de/) for software architecture documentation. 

For an intro into arc42: https://www.innoq.com/en/blog/brief-introduction-to-arc42/

## Features
- Cleaned up and Github compatible Markdown
- Rendering with [mdbook](https://rust-lang.github.io/mdBook/) and Github actions
- Diagrams with [mermaid](https://mermaid-js.github.io)
- Diagrams with [plantuml](https://plantuml.com/)

## Building locally
As preconditions the following tools must be available:
- cargo (the Rust package manager, used to install mdbook)
- npm (used to manage all javascript dependencies)
- plantuml (if plantuml is used for diagrams)

Install mdbook and the javascript dependencies:
```
cargo install mdbook
cargo install mdbook-mermaid
cargo install mdbook-plantuml
npm install
```

Build & open the book:
```
mdbook serve --open
```