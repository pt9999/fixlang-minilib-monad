# Minilib.Monad.Identity

Defined in minilib-monad@0.6.0

Identity monad

## Values

### namespace Minilib.Monad.Identity

#### get

Type: `Minilib.Monad.Identity::Identity a -> a`

Gets a value from an identity monad.

#### make

Type: `a -> Minilib.Monad.Identity::Identity a`

Creates an identity monad from a value.

## Types and aliases

### namespace Minilib.Monad.Identity

#### Identity

Defined as: `type Identity a = unbox struct { ...fields... }`

Identity monad

##### field `data`

Type: `a`

## Traits and aliases

## Trait implementations

### impl `Minilib.Monad.Identity::Identity : Std::Functor`

### impl `Minilib.Monad.Identity::Identity : Std::Monad`