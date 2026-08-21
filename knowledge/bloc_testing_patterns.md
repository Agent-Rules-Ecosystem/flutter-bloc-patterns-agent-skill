# 🧪 Pruebas Unitarias de BLoC (`bloc_test`)

```dart
blocTest<CounterBloc, int>(
  'emite [1] cuando se añade CounterIncremented',
  build: () => CounterBloc(),
  act: (bloc) => bloc.add(CounterIncremented()),
  expect: () => [1],
);
```
