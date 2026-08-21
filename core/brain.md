# 🧠 Engine de Decisiones BLoC (BLoC Brain)

## Matriz de Selección: ¿BLoC o Cubit?

1. **Usar Cubit si**:
   - El flujo es síncrono o de complejidad baja a media (ej. cambiar tema claro/oscuro, alternar un checkbox, formulario simple).
   - No se requiere transformar flujos de eventos (`debounce`, `throttle`, `switchMap`).

2. **Usar BLoC si**:
   - El flujo es reactivo complejo con múltiples eventos entrantes asíncronos.
   - Se requiere registrar o auditar la secuencia de eventos emitidos (`BlocObserver`).
   - Se requiere debounce / throttle en eventos de entrada (ej. barra de búsqueda).

3. **Usar HydratedBloc si**:
   - El estado debe persistir entre cierres de la app (ej. preferencia de usuario, token de sesión, carrito offline).
