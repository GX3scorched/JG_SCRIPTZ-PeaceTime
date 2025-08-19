# Peacetime (JG_SCRIPTZ) - ESX

Prevents players from attacking or causing damage while peacetime is active.

## Features
- Toggle peacetime via customizable command (default `/peacetime`)
- ESX group-based permission check (configurable)
- Integrates with `ox_lib` for notifications (if available)
- Compatible with `ox_target` (no direct target changes required)
- Optionally makes players invincible to prevent damage reliably
- Fully configurable via `config.lua`

## Installation
1. Drop `peacetime_jg_scriptz` into your server resources folder.
2. Ensure `ox_lib` and `ox_target` are installed and in `server.cfg` before this resource.
3. Add to `server.cfg`:
```
ensure ox_lib
ensure ox_target
ensure peacetime_jg_scriptz
```

## Configuration
Edit `config.lua` to change the command name, allowed groups, and behavior.

## Usage
- Staff with allowed group can run `/{command}` (default `/peacetime`) to toggle.
- You can also call the exported function from other resources:
```lua
local isOn = exports['peacetime_jg_scriptz']:isPeacetime()
exports['peacetime_jg_scriptz']:setPeacetime(true) -- turn on
```

## Notes & Limitations
- This resource uses a client-side approach to block controls and optionally sets players invincible.
- Client-side protection is fast and responsive, but server-side anti-cheat bypasses might still be possible on heavily-modded clients. For stronger enforcement, consider integrating server-side damage hooks or trusted anti-cheat checks.
- Tested with ESX shared object patterns. If you use a different ESX fork, minor adjustments may be needed.

Made by JG_SCRIPTZ
