# ⚙️ Flutter BLoC Patterns Skill Matrix & Directives

## 🎯 Capacidades de la Habilidad

```mermaid
graph LR
    Sub1[Sealed State Hierarchy] --> BlocCore[Flutter BLoC Skill]
    Sub2[HydratedBloc Persistence] --> BlocCore
    Sub3[bloc_test Suite] --> BlocCore
    Sub4[RxDart Transformers] --> BlocCore
    Sub5[BlocSelector & BuildWhen] --> BlocCore
```

---

## 📋 Protocolo de Auditoría BLoC (`$bloc:audit`)

1. **Auditoría de Widgets**:
   - ¿Se usan `BlocBuilder` masivos en la raíz del arbol de widgets? Sugerir extracción a sub-widgets más pequeños o `BlocSelector`.
   - ¿Se usa `BlocListener` para efectos secundarios (SnackBars, Navegación, Diálogos) en lugar de intentar meterlos en la función de build?
2. **Auditoría de BLoC**:
   - ¿Se instancian Repositorios dentro del BLoC en lugar de inyectarse por constructor?
   - ¿Los eventos tienen handlers debounced / throttled cuando aplican (ej. búsquedas autocomplete con `restartable()` o `debounce()`)?
3. **Auditoría de Pruebas**:
   - ¿Cada evento del BLoC posee al menos un `blocTest` que valida la transición exacta de estados?

---

## 🏗️ Estructura Canónica de Estado Sellado (Dart 3 Sealed Classes)

```dart
import 'package:equatable/equatable.dart';

sealed class FeatureState extends Equatable {
  const FeatureState();

  @override
  List<Object?> get props => [];
}

final class FeatureInitial extends FeatureState {}

final class FeatureLoading extends FeatureState {}

final class FeatureSuccess extends FeatureState {
  final List<DataModel> items;
  const FeatureSuccess(this.items);

  @override
  List<Object?> get props => [items];
}

final class FeatureFailure extends FeatureState {
  final String errorMessage;
  const FeatureFailure(this.errorMessage);

  @override
  List<Object?> get props => [errorMessage];
}
```
