# Commands

Below are the commands to use the macropad-tool.

## Validate the mapping against the device

```bash
sudo cargo run -- validate -c mapping_12key_4knob.ron -d
```

## Program the macropad

```bash
sudo cargo run -- program -c mapping_12key_4knob.ron
```

## Read the macropad

```bash
sudo cargo run -- read
```

## Set the LED mode

```bash
sudo cargo run -- led 4 1 purple
```

### Usage

```bash
Usage: macropad-tool led <INDEX> [LAYER] [LED_COLOR]

Arguments:

  <INDEX>      Index of LED modes
               --------0x8840----------
               0 - LEDs off
               1 - backlight always on with LedColor
               2 - no backlight, shock with LedColor when key pressed
               3 - no backlight, shock2 when LedColor when key pressed
               4 - no backlight, light up key with LedColor when pressed
               5 - backlight white always on
               --------0x8890---color is not supported-------
               0 - LEDs off
               1 - LED on for last pushed key
               2 - cycle through colors & buttons
  [LAYER]      [default: 1]
  [LED_COLOR]  Note: Not applicable for product id 0x8890
               Color to apply with mode [possible values: red, orange, yellow, green, cyan, blue, purple]
```
