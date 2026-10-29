# Sudoku Breeze remote config (kill switch)

`config.json` is the file the app reads at launch from `BreezeConfig.remoteConfigUrl`
(https://raw.githubusercontent.com/JycosDev/sudokubreeze-config/main/config.json), cached on the device; the app works
without it. It becomes the public repo `JycosDev/sudokubreeze-config`, like `JycosDev/golfbreeze-config` for Golf Breeze.
The kit's `RemoteConfig.cs` reads `features[]` (Golf Breeze's own file uses `courses[]`; the kit format is `features`).

- `features[].id` is the product id. `enabled: false` makes the Store row read `notice` (default "Temporarily unavailable")
  with a disabled CLOSED button, so nobody can buy while a problem is open. Owners keep what they bought: the game's
  `IsLocked` only looks at entitlements, so the switch stops sales, not play.
- `message` is shown once on the home screen when non-empty.
- raw.githubusercontent caches for about five minutes; devices pick a change up on their next launch.

Nothing here affects prices.
