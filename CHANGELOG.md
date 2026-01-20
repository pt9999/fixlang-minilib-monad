## 0.8.0
### Removed
- Moved Minilib.Monad.Error, Minilib.Monad.IO to minilib-common.

## 0.7.6
### Added
- Added Minilib.Monad.Yield. `Yield` is a simple generator monad, as well as an iterator.
- Minilib.Monad.Reader: Add `asks` function.
- Minilib.Monad.Reader: Update documents.
- Minilib.Monad.State: Update documents.

## 0.7.4
### Added
- Minilib.Monad.State: Add `SVar`, which is a variable bound to a substate of the State monad.

## 0.7.1
### Changed
- Minilib.Monad.Iden: Make `Iden` an alias for `Std::Identity`.

## 0.7.0
### Changed
- Minilib.Monad.Iden: Rename `Identity` to `Iden` to avoid collisions against `Std::Identity`.
