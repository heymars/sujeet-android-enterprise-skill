# Compose Guidelines

## Rules

- Use immutable UI state
- Keep composables focused
- Extract reusable components
- Avoid passing ViewModel directly into reusable composables
- Use rememberSaveable for configuration persistence

## State Management

Use:
- StateFlow
- collectAsStateWithLifecycle

Avoid:
- Mutable states scattered across composables

## Performance

- Use keys in LazyColumn
- Avoid recomposition-heavy calculations
- Use derivedStateOf
- Use remember for expensive objects

## Theming

- Material3 mandatory
- Centralized typography
- Centralized dimensions
- Dynamic colors optional