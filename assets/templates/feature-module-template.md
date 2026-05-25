# Feature Module Template

## Requirements

Generate enterprise-grade Android feature module.

## Module Structure

```text
feature/
 ├── data/
 │   ├── api/
 │   ├── dto/
 │   ├── repository/
 │   ├── local/
 │   └── mapper/
 │
 ├── domain/
 │   ├── model/
 │   ├── repository/
 │   └── usecase/
 │
 ├── ui/
 │   ├── screen/
 │   ├── component/
 │   ├── state/
 │   └── preview/
 │
 ├── navigation/
 │
 ├── di/
 │
 └── test/
```

## Requirements

Generated feature must include:
- Compose screen
- ViewModel
- UI state
- Navigation
- Repository
- UseCase
- API layer
- Room layer
- Dependency Injection
- Unit tests

## Rules

- Follow Clean Architecture
- Follow offline-first strategy
- Feature must be isolated
- Avoid direct module coupling
- Analytics support required
- Feature flags supported