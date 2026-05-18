# Offline First Strategy

## Principles

- Local DB is source of truth
- Network sync updates DB
- UI observes local DB

## Flow

API -> Repository -> Room -> UI

## Requirements

- Cache critical APIs
- Retry failed syncs
- Queue offline actions
- Handle sync conflicts gracefully