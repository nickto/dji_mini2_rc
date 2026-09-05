# DJI Mini2 RC as a Joystick

Connect your DJI Remote Controller to your PC and use it to play simulators.

- Currently confirmed working controllers: DJI Mini 2 RC (also known as RC-N1, RCS231, WM161b-RC-N1, RCN1)
- 16/02/2024 — added full support of 4 buttons that are mapped as joystick buttons
- Note: this code works on Linux only

> [!NOTE]
> This is a fork of [usatenko/DjiMini2RCasJoystick](https://github.com/usatenko/DjiMini2RCasJoystick)
> (which is itself a modified and improved version of [justin97530/miniDjiController](https://github.com/justin97530/miniDjiController)).
> The main difference is that this fork is packaged with [uv](https://docs.astral.sh/uv/),
> so the Python version and dependencies are managed by the project itself instead of manually.

## Usage

1. Install [uv](https://docs.astral.sh/uv/getting-started/installation/)
2. Connect your RC via the bottom Type-C USB connector to your laptop
3. Run:

   ```sh
   sudo uv run dji-mini2-rc -p /dev/ttyACM0
   ```

Your RC will be set to simulator mode and will pass stick values to the virtual joystick (`/dev/js0`).

## Tested joystick

Buttons that work are marked with arrows:

<p align="center">
  <img width="486" alt="Tested joystick buttons" src="https://github.com/usatenko/DjiMini2RCasJoystick/assets/1710344/b14e6429-550e-4727-9024-fc9d70a771a1">
</p>

## Notes

- This project works best on Python 3.10. The Python version is managed by `uv` (see `.python-version` and `pyproject.toml`), so you don't need to install or select it manually — `uv run` takes care of it.

## Troubleshooting

If you get `OSError: [Errno 19] Failed to open the uinput device: No such device`, run:

```sh
sudo modprobe uinput
```
