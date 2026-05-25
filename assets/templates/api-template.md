# API Layer Template

## Requirements

Generate scalable networking layer using:
- Retrofit
- OkHttp
- Kotlin Serialization
- Interceptors
- Result wrappers

## Rules

- Centralized error handling
- Logging interceptor
- Auth interceptor
- Timeout configuration
- API models separated from domain models

## Example API

```kotlin
interface FeatureApi {

    @GET("feature")
    suspend fun getFeature(): List<FeatureDto>
}
```

## DTO Rules

- DTOs belong in data layer
- Mapping mandatory
- Avoid nullable fields unless required

## Example Mapper

```kotlin
fun FeatureDto.toDomain(): Feature {
    return Feature(
        id = id,
        title = title
    )
}
```