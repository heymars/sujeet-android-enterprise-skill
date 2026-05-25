# Repository Template

## Requirements

Generate repository layer using:
- Clean Architecture
- Repository pattern
- Offline-first support
- Room + Retrofit integration

## Rules

- Repository handles data orchestration
- API DTOs should not reach UI
- Use mappers
- Support caching
- Handle exceptions centrally

## Example Structure

```kotlin
interface FeatureRepository {
    suspend fun getFeature(): Result<List<Feature>>
}
```

```kotlin
class FeatureRepositoryImpl @Inject constructor(
    private val api: FeatureApi,
    private val dao: FeatureDao
) : FeatureRepository {

    override suspend fun getFeature(): Result<List<Feature>> {
        return runCatching {
            val remoteData = api.getFeature()

            dao.insert(remoteData.map { it.toEntity() })

            dao.getAll().map { it.toDomain() }
        }
    }
}
```