# Clean Architecture Guidelines

## Layers

### Presentation Layer
Contains:
- Compose UI
- ViewModels
- UI State
- Navigation

### Domain Layer
Contains:
- Use Cases
- Domain Models
- Repository Interfaces

### Data Layer
Contains:
- Retrofit APIs
- DTOs
- Room DB
- Repository Implementations
- Mappers

## Rules

- Domain layer should not depend on Android framework
- Data layer implements domain contracts
- Presentation layer depends on domain
- Dependency direction must remain inward

## Recommended Pattern

UI -> ViewModel -> UseCase -> Repository -> API/DB