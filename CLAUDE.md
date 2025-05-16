# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains ZMK firmware configuration for a wireless Corne split keyboard with nice!nano controllers. ZMK is a keyboard firmware built on the Zephyr RTOS, focused on wireless, split keyboards.

## Development Commands

### Building Firmware

The firmware is built automatically using GitHub Actions whenever changes are pushed to the repository. The workflow is configured in `build.yaml`.

There is no local build process documented. Typical workflow:
1. Make changes to `config/corne.keymap`
2. Push changes to GitHub
3. GitHub Actions builds the firmware
4. Download artifacts from GitHub Actions
5. Flash to keyboard

### Flashing Firmware

To flash the keyboard with new firmware:

1. Put the keyboard into bootloader mode by pressing the reset button twice or short circuit `RST` and `GND` pins
2. Connect keyboard to computer with a proper USB-C cable (not magnetic)
3. Copy the left firmware to the `NICENANO` storage
4. Repeat for the right side

## Repository Structure

- `config/corne.keymap`: Main keymap configuration file
- `config/corne.conf`: Keyboard configuration options
- `config/west.yml`: ZMK dependencies configuration
- `build.yaml`: GitHub Actions build configuration
- `screenshots/`: Keymap layer visualizations

## Keymap Overview

The keyboard has multiple layers:
- Layer 0 (DEFAULT): Standard QWERTY layout
- Layer 1 (LOWER): Symbols, media controls, and navigation
- Layer 2 (RAISE): Numbers and more symbols
- Layer 3 (TOP): Function keys and more

## Editing Keymaps

Two methods for editing keymaps:
1. Use the [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) and push changes to GitHub
2. Directly edit `config/corne.keymap` following ZMK syntax and structure

## Troubleshooting

If split keyboard halves are unable to pair, you may need to flash the reset firmware. See the [ZMK troubleshooting guide](https://zmk.dev/docs/troubleshooting#split-keyboard-halves-unable-to-pair).