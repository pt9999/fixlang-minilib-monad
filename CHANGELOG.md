## 0.10.0
### Changed
- Minilib.Monad.Result: Changed the implementation of `MonadIOFailIF`, also changed its behavior.
  * For details, see document comment of the implementation of `MonadIOFailIF`.
### Added
- Minilib.Monad.Iden: Added `identity`, `run_identity`, `lift_identity`.

## 0.9.0
### Added
- Added Minilib.Monad.Alt.
- Minilib.Monad.Cont: Added `map_cont_t`, `map_cont`.
- Minilib.Monad.Result: Added `map_result_t`, `from_iofail`, `to_iofail`.

## 0.8.2
### Added
- Minilib.Monad.Cont: Added `eval_cont_t`, `eval_cont`, impls of `MonadIOIF`, `MonadIOFailIF`, `MonadError`.

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
