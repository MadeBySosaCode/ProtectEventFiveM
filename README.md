# FiveM Event Protector Script

This script obfuscates and protects FiveM Lua scripts by dynamically generating random event names for registered events, event handlers, and triggered server events. The source code will be compiled, so end users will not see the original script content, adding an extra layer of protection.

## Features

- Obfuscates `RegisterNetEvent` calls by renaming event names to random strings.
- Modifies `AddEventHandler` to match the obfuscated event names.
- Adds a safety check for `TriggerServerEvent`, ensuring the event is valid before attempting to trigger.
- Works recursively through all `.lua` files in a specified directory (default is `./resources/`).
- Compiled into an executable, ensuring the source code is hidden from end users.

## Usage

1. Clone or download the repository.
2. Place the script in your FiveM server directory where you want to obfuscate the Lua files.
3. Modify the `scripts_directory` variable in the script to point to the folder where your Lua scripts are located (by default, it's `./resources/`).
4. Compile the script into an executable using a Python-to-executable compiler like `pyinstaller` or `cx_Freeze`.
   
   Example using `pyinstaller`:

   ```bash
   pyinstaller --onefile obfuscate_events.py
