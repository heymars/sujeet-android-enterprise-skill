# Room Database Template

## Requirements

Generate Room layer using:
- Entities
- DAO
- TypeConverters
- Offline-first principles

## Rules

- Entities separated from domain models
- Use suspend DAO methods
- Use Flow for observation
- Index important columns

## Example Entity

```kotlin
@Entity(tableName = "features")
data class FeatureEntity(
    @PrimaryKey
    val id: String,
    val title: String
)
```

## Example DAO

```kotlin
@Dao
interface FeatureDao {

    @Query("SELECT * FROM features")
    fun observeAll(): Flow<List<FeatureEntity>>

    @Insert(onConflict = OnConflictStrategy.REPLACE)
    suspend fun insert(items: List<FeatureEntity>)
}
```