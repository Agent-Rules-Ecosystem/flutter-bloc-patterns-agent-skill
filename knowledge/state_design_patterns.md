# 🧊 Patrones de Diseño de Estado

1. **Sealed Class Hierarchy (Dart 3)**:
   ```dart
   sealed class AuthState extends Equatable {}
   final class Unauthenticated extends AuthState {}
   final class Authenticated extends AuthState { final User user; ... }
   ```

2. **CopyWith Pattern para Formularios y Filtros**:
   ```dart
   class FilterState extends Equatable {
     final String query;
     final bool isAscending;

     FilterState copyWith({String? query, bool? isAscending}) =>
       FilterState(query: query ?? this.query, isAscending: isAscending ?? this.isAscending);
   }
   ```
