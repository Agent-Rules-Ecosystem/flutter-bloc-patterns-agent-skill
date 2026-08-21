# 🏛️ Guía de Arquitectura BLoC en Flutter

## Capas de la Aplicación

1. **Presentation Layer (UI)**: Widgets puros que utilizan `BlocBuilder`, `BlocListener` o `BlocConsumer`.
2. **Domain/Business Logic Layer (BLoC)**: Procesa eventos recibidos de la UI y emite nuevos estados inmutables.
3. **Data Layer (Repository)**: Abstrae la procedencia de los datos (APIs REST, GraphQL, Firebase, SQLite/Isar).
