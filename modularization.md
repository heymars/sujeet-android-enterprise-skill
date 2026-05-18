# Modularization Strategy

## Recommended Modules

:app
:core:ui
:core:network
:core:database
:core:designsystem
:core:analytics
:core:common
:feature:home
:feature:profile
:feature:payments

## Rules

- Features should be isolated
- Shared utilities belong in core
- Avoid circular dependencies
- Feature modules should expose public APIs only