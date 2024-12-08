# `module Minilib.Functor.Pair`

# Types and aliases

## `namespace Minilib.Functor.Pair`

### `type PairL r l = unbox struct { ...fields... }`

A functor on the left component. This is a swapped version of `Tuple2`.

#### field `data : (l, r)`

### `type [f : *->*] PairLT r f l = unbox struct { ...fields... }`

A functor on the left component with an underlying functor.

#### field `data : f (l, r)`

### `type PairR l r = unbox struct { ...fields... }`

A functor on the right component. This is same as `Tuple2`.

#### field `data : (l, r)`

### `type [f : *->*] PairRT l f r = unbox struct { ...fields... }`

A functor on the right component with an underlying functor.

#### field `data : f (l, r)`

# Traits and aliases

# Trait implementations

### `impl Minilib.Functor.Pair::PairL r : Std::Functor`

### `impl [f : Std::Functor] Minilib.Functor.Pair::PairLT r f : Std::Functor`

### `impl Minilib.Functor.Pair::PairR l : Std::Functor`

### `impl [f : Std::Functor] Minilib.Functor.Pair::PairRT l f : Std::Functor`

# Values

## `namespace Minilib.Functor.Pair::PairL`

### `@data : Minilib.Functor.Pair::PairL r l -> (l, r)`

Retrieves the field `data` from a value of `PairL`.

### `act_data : [f : Std::Functor] ((l, r) -> f (l, r)) -> Minilib.Functor.Pair::PairL r l -> f (Minilib.Functor.Pair::PairL r l)`

Updates a value of `PairL` by applying a functorial action to field `data`.

### `get : Minilib.Functor.Pair::PairL r l -> (l, r)`

### `make : (l, r) -> Minilib.Functor.Pair::PairL r l`

### `mod_data : ((l, r) -> (l, r)) -> Minilib.Functor.Pair::PairL r l -> Minilib.Functor.Pair::PairL r l`

Updates a value of `PairL` by applying a function to field `data`.

### `set_data : (l, r) -> Minilib.Functor.Pair::PairL r l -> Minilib.Functor.Pair::PairL r l`

Updates a value of `PairL` by setting field `data` to a specified one.

## `namespace Minilib.Functor.Pair::PairLT`

### `@data : Minilib.Functor.Pair::PairLT r f l -> f (l, r)`

Retrieves the field `data` from a value of `PairLT`.

### `act_data : [f : Std::Functor] (f (l, r) -> f (f (l, r))) -> Minilib.Functor.Pair::PairLT r f l -> f (Minilib.Functor.Pair::PairLT r f l)`

Updates a value of `PairLT` by applying a functorial action to field `data`.

### `get : Minilib.Functor.Pair::PairLT r f l -> f (l, r)`

### `make : f (l, r) -> Minilib.Functor.Pair::PairLT r f l`

### `mod_data : (f (l, r) -> f (l, r)) -> Minilib.Functor.Pair::PairLT r f l -> Minilib.Functor.Pair::PairLT r f l`

Updates a value of `PairLT` by applying a function to field `data`.

### `set_data : f (l, r) -> Minilib.Functor.Pair::PairLT r f l -> Minilib.Functor.Pair::PairLT r f l`

Updates a value of `PairLT` by setting field `data` to a specified one.

## `namespace Minilib.Functor.Pair::PairR`

### `@data : Minilib.Functor.Pair::PairR l r -> (l, r)`

Retrieves the field `data` from a value of `PairR`.

### `act_data : [f : Std::Functor] ((l, r) -> f (l, r)) -> Minilib.Functor.Pair::PairR l r -> f (Minilib.Functor.Pair::PairR l r)`

Updates a value of `PairR` by applying a functorial action to field `data`.

### `get : Minilib.Functor.Pair::PairR l r -> (l, r)`

### `make : (l, r) -> Minilib.Functor.Pair::PairR l r`

### `mod_data : ((l, r) -> (l, r)) -> Minilib.Functor.Pair::PairR l r -> Minilib.Functor.Pair::PairR l r`

Updates a value of `PairR` by applying a function to field `data`.

### `set_data : (l, r) -> Minilib.Functor.Pair::PairR l r -> Minilib.Functor.Pair::PairR l r`

Updates a value of `PairR` by setting field `data` to a specified one.

## `namespace Minilib.Functor.Pair::PairRT`

### `@data : Minilib.Functor.Pair::PairRT l f r -> f (l, r)`

Retrieves the field `data` from a value of `PairRT`.

### `act_data : [f : Std::Functor] (f (l, r) -> f (f (l, r))) -> Minilib.Functor.Pair::PairRT l f r -> f (Minilib.Functor.Pair::PairRT l f r)`

Updates a value of `PairRT` by applying a functorial action to field `data`.

### `get : Minilib.Functor.Pair::PairRT l f r -> f (l, r)`

### `make : f (l, r) -> Minilib.Functor.Pair::PairRT l f r`

### `mod_data : (f (l, r) -> f (l, r)) -> Minilib.Functor.Pair::PairRT l f r -> Minilib.Functor.Pair::PairRT l f r`

Updates a value of `PairRT` by applying a function to field `data`.

### `set_data : f (l, r) -> Minilib.Functor.Pair::PairRT l f r -> Minilib.Functor.Pair::PairRT l f r`

Updates a value of `PairRT` by setting field `data` to a specified one.