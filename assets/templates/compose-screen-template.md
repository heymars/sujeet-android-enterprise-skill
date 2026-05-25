# Compose Screen Template

## Requirements

Generate a production-ready Compose screen using:
- Material3
- Stateless composables
- State hoisting
- Preview support
- Loading/Error/Success states
- Accessibility support

## Structure

```text
feature/
 ├── ui/
 │   ├── FeatureScreen.kt
 │   ├── FeatureContent.kt
 │   ├── FeatureLoading.kt
 │   ├── FeatureError.kt
 │   ├── FeaturePreview.kt
```

## Rules

- No business logic inside composables
- Use immutable UI state
- Use collectAsStateWithLifecycle
- Extract reusable components
- Avoid large composables
- Support dark theme

## Example State

```kotlin
data class FeatureUiState(
    val isLoading: Boolean = false,
    val data: List<Item> = emptyList(),
    val error: String? = null
)
```

## Preview Required

Every reusable composable must include Preview.