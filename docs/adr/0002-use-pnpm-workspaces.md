# ADR-0002: Use pnpm Workspaces

## Status

Accepted

## Date

2026-08-09

---

## Context

CommerceHub is organized as a monorepo containing multiple applications and shared packages. The project requires a workspace solution that can:

- Manage dependencies across multiple packages
- Link local packages without publishing them
- Reduce disk space by avoiding duplicate installations
- Support modern JavaScript and TypeScript tooling
- Integrate well with build orchestration tools

A workspace manager is required to efficiently manage dependencies and package relationships within the repository.

---

## Decision

CommerceHub will use **pnpm Workspaces** as the package manager and workspace solution.

pnpm provides efficient dependency management through a content-addressable store, supports workspace linking, and integrates seamlessly with modern monorepo tooling such as Turborepo.

---

## Decision Drivers

The following factors influenced this decision:

- Efficient dependency management
- Fast installation performance
- Native workspace support
- Reduced disk usage
- Strong TypeScript ecosystem support
- Compatibility with Turborepo

---

## Alternatives Considered

### Option 1: npm Workspaces

**Pros**

- Built into Node.js
- No additional package manager required
- Familiar to most developers

**Cons**

- Slower dependency installation for larger workspaces
- Less efficient disk usage
- Fewer advanced workspace features

---

### Option 2: Yarn Workspaces

**Pros**

- Mature workspace support
- Widely adopted
- Good developer experience

**Cons**

- Multiple Yarn versions can introduce inconsistency
- Team preference is toward pnpm
- No significant advantage for this project

---

### Option 3: pnpm Workspaces (Selected)

**Pros**

- Fast installations
- Efficient disk usage through a shared package store
- Excellent monorepo support
- Native workspace linking
- Well suited for TypeScript projects
- Strong integration with Turborepo

**Cons**

- Requires familiarity with pnpm-specific commands
- Some developers may be less familiar with the package manager

---

## Consequences

### Positive

- Faster dependency installation.
- Shared packages can be referenced without publishing.
- Reduced storage requirements.
- Consistent dependency management across all applications.
- Scales well as additional applications and packages are introduced.

### Negative

- Developers unfamiliar with pnpm may require a short learning period.
- Some third-party tooling may assume npm by default, requiring minor configuration.

---

## Future Considerations

This decision should be revisited if:

- The Node.js ecosystem significantly changes its recommended package management approach.
- Workspace requirements become incompatible with pnpm.
- Tooling support for pnpm becomes a limiting factor.

At the current scale and anticipated growth of CommerceHub, pnpm provides the best balance of performance, simplicity, and maintainability.

---

## References

- https://pnpm.io/
- https://pnpm.io/workspaces