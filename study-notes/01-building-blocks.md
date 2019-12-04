# TIL Gatsby

## Creating Components

### What do they look like?
Functional components
export default at the top
no need to state const
can take in props

### Pages

Every javascript component defined in the pages directory automatically becomes a page and can be referenced in the browser (ie. localhost:8000/about)

That could eliminate the need for React Router?

### Sub-Components
**Sub-components** are reusable pieces that can be applied throughout an app

For example:
1. Buttons
2. Headers

### Links

Gatsby has a link component used **only** for directing between internal pages

For external pages, use standard anchor tag
index has url of '/'