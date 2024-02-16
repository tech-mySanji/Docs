
What is state management ?

State management in Flutter is all about handling the data that changes your app's UI and how that data interacts with user actions. It's crucial for building complex apps where multiple screens or widgets need to share and update data consistently.

Here's a breakdown of the key points:

**Why it's important:**

- **Sharing data:** As your app grows, passing data manually between screens becomes cumbersome and error-prone. State management provides a central location to store and access shared data.
- **Maintaining consistency:** Ensures all parts of your UI reflect the latest state of the data, avoiding inconsistencies and bugs.
- **Improved scalability:** Makes it easier to manage complex app structures and simplifies adding new features.

TLDR; Extract business logic from the widgets and React to state -  changes anywhere in the app. Any changes in the app will be the side effect of some changes.


**1. BLoC (Business Logic Component):**

- Acts as a central hub for managing app state and business logic.
- Separates UI logic from business logic, improving code organization and maintainability.
- Listens for events (user actions or other changes) and emits new states based on those events.

**2. Events:**

- Represent user interactions or other changes that trigger state updates.
- Usually simple data classes describing the action taken.
- Ex: `ButtonPressedEvent` for pressing a button, `FetchedUserDataEvent` for fetching user data.

**3. States:**

- Represent the current state of the app's data at any given time.
- Typically immutable data classes holding relevant information.
- Ex: `LoggedInState` containing user data, `LoadingState` while fetching data, `ErrorState` for errors.

**4. BlocProvider:**

- Makes a specific Bloc instance accessible to its child widgets.
- Allows widgets to dispatch events to the Bloc and react to state changes.

**5. BlocBuilder:**

- Listens for state changes from a Bloc and rebuilds the UI based on the current state.
- Provides flexibility to customize how UI rebuilds based on specific state changes.

**6. BlocConsumer:**

- Combines the functionalities of BlocBuilder and BlocListener.
- Listens for state changes and rebuilds the UI, while also offering optional side effects based on specific states.

**7. BlocListener:**

- Listens for state changes from a Bloc and performs side effects, like showing snackbars or navigating to other screens.

**8. BlocDelegate:**

- Optional component for logging Bloc events and states, aiding in debugging and understanding app behavior.


I've huge app, how do i manage the dependency of lot of BLOC's ?
![[Pasted image 20240216195449.png]]

```
class MyApp extends StatelessWidget {
	@override Widget build(BuildContext context) { 
		return MultiBlocProvider( providers: [ 
				BlocProvider<CounterBloc>( create: (context) => CounterBloc(), ), BlocProvider<ThemeBloc>( create: (context) => ThemeBloc(), ), ],
				 child: MaterialApp( home: MyHomePage(), ), );
 } }

```

https://www.youtube.com/watch?v=knMvKPKBzGE
https://pub.dev/packages/flutter_bloc
https://pub.dev/packages/bloc_test