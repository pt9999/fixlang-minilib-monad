# `module Minilib.Monad.State`

State Monad which maintains a mutable state.

# Types and aliases

## `namespace Minilib.Monad.State`

### `type State = Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a`

### `type [m : *->*] StateResultT a m s = unbox struct { ...fields... }`

------------------------------------------------------------------------
Looks similar to WriterT, but this is a functor against `s`, ie. the left part of Tuple2.

#### field `data : m (s, a)`

### `type [m : *->*] StateT s m a = unbox struct { ...fields... }`

State monad wraps a function from a initial state to a pair of a value and a final state.

#### field `data : s -> m (s, a)`

# Traits and aliases

## `namespace Minilib.Monad.State`

### `trait [sm : *->*] sm : MonadStateIF`

A trait for generic state monads that manages the internal state.

#### associated type `StateType sm`

The type of the internal state.

#### method `get_state : sm (Minilib.Monad.State::MonadStateIF::StateType sm)`

A monad that returns the internal state as a value.

#### method `put_state : Minilib.Monad.State::MonadStateIF::StateType sm -> sm ()`

A monad that puts the specified value to the internal state.

# Trait implementations

### `impl [m : Std::Monad] Minilib.Monad.State::StateResultT a m : Std::Functor`

### `impl Minilib.Monad.State::StateT s : Minilib.Monad.Trans::MonadTrans`

### `impl [m : Minilib.Monad.Error::MonadError] Minilib.Monad.State::StateT s m : Minilib.Monad.Error::MonadErrorIF`

### `impl [m : Minilib.Monad.IO::MonadIOFail] Minilib.Monad.State::StateT s m : Minilib.Monad.IO::MonadIOFailIF`

### `impl [m : Minilib.Monad.IO::MonadIO] Minilib.Monad.State::StateT s m : Minilib.Monad.IO::MonadIOIF`

### `impl [m : Std::Monad] Minilib.Monad.State::StateT s m : Minilib.Monad.State::MonadStateIF`

### `impl [m : Std::Monad] Minilib.Monad.State::StateT s m : Std::Functor`

### `impl [m : Std::Monad] Minilib.Monad.State::StateT s m : Std::Monad`

# Values

## `namespace Minilib.Monad.State`

### `eval_state : s -> Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a -> a`

Runs a State monad with the supplied initial state and return the final value, discarding the final state.

### `eval_state_t : [m : Std::Monad] s -> Minilib.Monad.State::StateT s m a -> m a`

Runs a StateT monad with the supplied initial state and return the final value, discarding the final state.

### `exec_state : s -> Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a -> s`

Runs a State monad with the supplied initial state and return the final state, discarding the final value.

### `exec_state_t : [m : Std::Monad] s -> Minilib.Monad.State::StateT s m a -> m s`

Runs a StateT monad with the supplied initial state and return the final state, discarding the final value.

### `lens_state : ((s -> Minilib.Monad.State::StateResultT a Minilib.Monad.Identity::Identity s) -> t -> Minilib.Monad.State::StateResultT a Minilib.Monad.Identity::Identity t) -> Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a -> Minilib.Monad.State::StateT t Minilib.Monad.Identity::Identity a`

### `lens_state_t : [m : Std::Monad] ((s -> Minilib.Monad.State::StateResultT a m s) -> t -> Minilib.Monad.State::StateResultT a m t) -> Minilib.Monad.State::StateT s m a -> Minilib.Monad.State::StateT t m a`

Transforms a state monad with an lens action.
For example, if `Foo` has a field `bar: Bar`, then `act_bar` is a function of type
`[f: Functor] (bar -> f bar) -> (foo -> f foo)`.
Using `act_bar`, a state monad of `Bar` can be transformed to a state monad of `Foo`.
```
change_bar: StateT Bar IO ();
change_bar = ...;
change_foo: StateT Foo IO ();
change_foo = change_bar.lens_state_t(Foo::act_bar);
```
Note that `act_xxx` can be composed, for example `Foo::act_bar << Bar::act_baz << Baz::act_qux`.

### `make_state_monad : (s -> (s, a)) -> Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a`

Creates a State monad from a function.

### `make_state_t_monad : [m : Std::Monad] (s -> m (s, a)) -> Minilib.Monad.State::StateT s m a`

Creates a StateT monad from a function.

### `map_state_t : [m : Std::Monad, n : Std::Monad] (m (s, a) -> n (s, a)) -> Minilib.Monad.State::StateT s m a -> Minilib.Monad.State::StateT s n b`

Maps both the return value and final state.

### `mod_state : [sm : Minilib.Monad.State::MonadState] (Minilib.Monad.State::MonadStateIF::StateType sm -> Minilib.Monad.State::MonadStateIF::StateType sm) -> sm ()`

A monad that modifies the current state with the specified function.

### `run_state : s -> Minilib.Monad.State::StateT s Minilib.Monad.Identity::Identity a -> (s, a)`

Runs a State monad with the supplied initial state.

### `run_state_t : [m : Std::Monad] s -> Minilib.Monad.State::StateT s m a -> m (s, a)`

Runs a StateT monad with the supplied initial state.

## `namespace Minilib.Monad.State::MonadStateIF`

### `get_state : [sm : Minilib.Monad.State::MonadStateIF] sm (Minilib.Monad.State::MonadStateIF::StateType sm)`

A monad that returns the internal state as a value.

### `put_state : [sm : Minilib.Monad.State::MonadStateIF] Minilib.Monad.State::MonadStateIF::StateType sm -> sm ()`

A monad that puts the specified value to the internal state.

## `namespace Minilib.Monad.State::StateResultT`

### `@data : Minilib.Monad.State::StateResultT a m s -> m (s, a)`

Retrieves the field `data` from a value of `StateResultT`.

### `act_data : [f : Std::Functor] (m (s, a) -> f (m (s, a))) -> Minilib.Monad.State::StateResultT a m s -> f (Minilib.Monad.State::StateResultT a m s)`

Updates a value of `StateResultT` by applying a functorial action to field `data`.

### `make : m (s, a) -> Minilib.Monad.State::StateResultT a m s`

### `mod_data : (m (s, a) -> m (s, a)) -> Minilib.Monad.State::StateResultT a m s -> Minilib.Monad.State::StateResultT a m s`

Updates a value of `StateResultT` by applying a function to field `data`.

### `set_data : m (s, a) -> Minilib.Monad.State::StateResultT a m s -> Minilib.Monad.State::StateResultT a m s`

Updates a value of `StateResultT` by setting field `data` to a specified one.

## `namespace Minilib.Monad.State::StateT`

### `@data : Minilib.Monad.State::StateT s m a -> s -> m (s, a)`

Retrieves the field `data` from a value of `StateT`.

### `act_data : [f : Std::Functor] ((s -> m (s, a)) -> f (s -> m (s, a))) -> Minilib.Monad.State::StateT s m a -> f (Minilib.Monad.State::StateT s m a)`

Updates a value of `StateT` by applying a functorial action to field `data`.

### `mod_data : ((s -> m (s, a)) -> s -> m (s, a)) -> Minilib.Monad.State::StateT s m a -> Minilib.Monad.State::StateT s m a`

Updates a value of `StateT` by applying a function to field `data`.

### `set_data : (s -> m (s, a)) -> Minilib.Monad.State::StateT s m a -> Minilib.Monad.State::StateT s m a`

Updates a value of `StateT` by setting field `data` to a specified one.