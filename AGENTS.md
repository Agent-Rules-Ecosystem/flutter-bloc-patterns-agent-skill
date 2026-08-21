---
name: flutter-bloc-patterns-agent-skill
description: Flutter BLoC Architecture, Reactive State Management, HydratedBloc, and BlocTest Skill for AI Agents.
---

# 🧱 Flutter BLoC Patterns Skill Directive

## Bootstrap de la Habilidad

Al detectar `$bloc` o tareas relacionadas con BLoC, Cubit, `flutter_bloc`, `bloc_test`, `HydratedBloc`, o gestión de estado reactivo en Flutter:

1. `.agents/skills/flutter-bloc/SKILL.md` ← **Directiva principal**
2. `.agents/skills/flutter-bloc/core/commands.md`
3. `.agents/skills/flutter-bloc/core/brain.md`
4. `.agents/skills/flutter-bloc/core/path_map.md`

## Reglas Canónicas de BLoC en Flutter

- **Cero Lógica de Negocio en la UI**: Los widgets solo leen estados y disparan eventos.
- **Estados Inmutables**: Todos los estados deben extender `Equatable` o usar Dart 3 `sealed class`.
- **Inyección de Dependencias Limpia**: Proveer Repositorios mediante `RepositoryProvider` o `GetIt` e inyectarlos en el constructor del BLoC.
- **Manejo de Errores Tipados**: Los estados de fallo deben contener un objeto de error tipado (`Failure` domain model) en lugar de cadenas de texto crudas.
