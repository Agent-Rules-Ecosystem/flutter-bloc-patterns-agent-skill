# 🧱 BLoC Pattern Template

```dart
import 'package:flutter_bloc/flutter_bloc.dart';
import 'package:equatable/equatable.dart';

// Eventos
abstract class SampleEvent extends Equatable {
  const SampleEvent();
  @override
  List<Object?> get props => [];
}

class FetchSampleData extends SampleEvent {}

// Estados
sealed class SampleState extends Equatable {
  const SampleState();
  @override
  List<Object?> get props => [];
}

final class SampleInitial extends SampleState {}
final class SampleLoading extends SampleState {}
final class SampleSuccess extends SampleState {
  final List<String> items;
  const SampleSuccess(this.items);
  @override
  List<Object?> get props => [items];
}

// BLoC
class SampleBloc extends Bloc<SampleEvent, SampleState> {
  SampleBloc() : super(SampleInitial()) {
    on<FetchSampleData>((event, emit) async {
      emit(SampleLoading());
      await Future.delayed(const Duration(seconds: 1));
      emit(const SampleSuccess(["Item 1", "Item 2"]));
    });
  }
}
```
