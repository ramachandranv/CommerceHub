# ADR-0003: Use Next.js for the Web Application

## Status

Accepted

## Date

2026-09-27

---

## Context

CommerceHub is an online retail platform that requires a modern web application for customers to browse products, view product details, manage their cart, complete checkout, and track orders.

The application will need to support:

- Fast initial page loads
- Search-engine-friendly product and category pages
- Server-side data fetching where appropriate
- Client-side interactivity for features such as cart and checkout
- Scalable routing and application structure
- TypeScript support
- Integration with the CommerceHub backend APIs

A frontend framework needs to be selected that can support these requirements while also providing a productive development experience.

The project owner already has professional experience with React and Next.js, which provides an existing foundation for building and maintaining the application.

---

## Decision

CommerceHub will use **Next.js with TypeScript** for the customer-facing web application.

The application will use the Next.js App Router and will adopt server-side rendering and client-side rendering selectively based on the requirements of each feature.

Next.js will be responsible for the web application layer, while backend business logic and persistent data management will be handled by the CommerceHub backend services.

---

## Decision Drivers

The decision was influenced by:

- Performance
- SEO requirements for an e-commerce application
- Server-side rendering capabilities
- React ecosystem
- TypeScript support
- Routing and application structure
- Developer productivity
- Existing project experience with Next.js

---

## Alternatives Considered

### Option 1: React with a separate frontend framework

A React application could be built using a client-side framework or custom tooling.

**Pros**

- Flexible architecture
- Full control over application tooling
- Familiar React ecosystem

**Cons**

- Additional configuration required
- SEO and server rendering require additional solutions
- More infrastructure decisions would need to be made

---

### Option 2: Angular

**Pros**

- Full-featured application framework
- Strong TypeScript support
- Established enterprise ecosystem

**Cons**

- Different programming model from the team's existing React experience
- Additional learning overhead
- Not required for the current CommerceHub requirements

---

### Option 3: Next.js (Selected)

**Pros**

- Built on React
- Supports server and client rendering
- Strong support for e-commerce use cases
- Built-in routing
- TypeScript support
- Good developer experience
- Allows the project to build on existing React and Next.js experience

**Cons**

- Introduces Next.js-specific concepts and conventions
- Requires understanding of server and client component boundaries
- Some framework behavior differs from a traditional client-side React application

---

## Consequences

### Positive

- CommerceHub can build on the existing React and Next.js knowledge of the project owner.
- Product and category pages can take advantage of server rendering and SEO capabilities.
- The application can combine server-side and client-side functionality as required.
- Next.js provides a structured foundation for the customer-facing application.
- The project can gradually adopt more advanced Next.js capabilities as requirements emerge.

### Negative

- The project will need to follow Next.js conventions.
- Developers will need to understand the differences between Server Components and Client Components.
- Some decisions around data fetching and rendering will require careful consideration.

---

## Future Considerations

The Next.js architecture will be revisited if CommerceHub develops requirements that cannot be reasonably supported by the framework or if a different frontend architecture provides significant technical or business benefits.

The project will avoid adopting advanced Next.js features solely because they are available. Features will be introduced when they solve a concrete requirement.

---

## References

- Next.js Documentation
- React Documentation