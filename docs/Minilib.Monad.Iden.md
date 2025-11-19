# Minilib.Monad.Iden

Defined in minilib-monad@0.7.0

Identity monad

## Values

### namespace Minilib.Monad.Iden

#### get

Type: `Minilib.Monad.Iden::Iden a -> a`

Gets a value from an identity monad.

#### make

Type: `a -> Minilib.Monad.Iden::Iden a`

Creates an identity monad from a value.

## Types and aliases

### namespace Minilib.Monad.Iden

#### Iden

Defined as: `type Iden a = unbox struct { ...fields... }`

Identity monad

##### field `data`

Type: `a`

## Traits and aliases

## Trait implementations

### impl `Minilib.Monad.Iden::Iden : Std::Functor`

### impl `Minilib.Monad.Iden::Iden : Std::Monad`