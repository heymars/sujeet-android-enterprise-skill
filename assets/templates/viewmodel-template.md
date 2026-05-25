# ViewModel Template

## Requirements

Generate a scalable ViewModel using:
- Hilt
- StateFlow
- Coroutines
- Clean Architecture
- Immutable state

## Rules

- ViewModel should not access Retrofit directly
- Business logic belongs in UseCases
- Expose immutable StateFlow
- Handle loading/success/error states
- Use viewModelScope

## Example Structure

```kotlin
@HiltViewModel
class FeatureViewModel @Inject constructor(
    private val getFeatureUseCase: GetFeatureUseCase
) : ViewModel() {

    private val _uiState = MutableStateFlow(FeatureUiState())
    val uiState = _uiState.asStateFlow()

    fun loadData() {
        viewModelScope.launch {
            _uiState.update {
                it.copy(isLoading = true)
            }

            runCatching {
                getFeatureUseCase()
            }.onSuccess { result ->
                _uiState.update {
                    it.copy(
                        isLoading = false,
                        data = result
                    )
                }
            }.onFailure { throwable ->
                _uiState.update {
                    it.copy(
                        isLoading = false,
                        error = throwable.message
                    )
                }
            }
        }
    }
}
```