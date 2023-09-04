# How to flash

This is the configuration for a BT60 wireless mechanical keyboard. To flash it, do the following:

1. Visit [the Actions screen](../../actions?query=branch%3Abt60-custom) screen of this repository (and filter for this branch).
2. Download the latest build's `firmware.zip` file, and extract the `[whatever].uf2` file from it
3. Plug the keyboard into your computer, and put it in boot mode (e.g., double-tap the reset button). It should mount as a USB storage device on your computer.
4. Drag `[whatever].uf2` into the root folder of the new mounted drive.

To update the key mappings, update the `config/bt60.keymap` file in *this* branch (after reading [the ZMK docs](https://zmk.dev/docs)). A new build should appear in [the Actions screen](../../actions?query=branch%3Abt60-custom).

(The rest of this README came from [PolarityWorks/zmk-config-ckp](https://github.com/PolarityWorks/zmk-config-ckp).)

# Where this came from

This is a clone of the [PolarityWorks/zmk-config-ckp (branch bt60-ANSI)](https://github.com/PolarityWorks/zmk-config-ckp/tree/bt60-ANSI) repository which contains the source code for the BT60 keyboard's ZMK firmware. The key mappings are customized to a custom layout.

# Local builds

Steps taken from [ZMK Development Setup](https://zmk.dev/docs/development/setup). Commands have been provided where the steps differ from the documentation. Tested on Ubuntu 20.04.

1. [Install prerequisites](https://zmk.dev/docs/development/setup#prerequisites)
2. [Install `west`](https://zmk.dev/docs/development/setup#west-installation)
3. [Install toolchain](https://zmk.dev/docs/development/setup#toolchain-installation)
4. [Initialize West]([Initialize West](https://zmk.dev/docs/development/setup#initialize-west))
    ```
    west init -l config
    ```
5. [Update To Fetch Modules](https://zmk.dev/docs/development/setup#update-to-fetch-modules)
6. [Export Zephyr™ Core](https://zmk.dev/docs/development/setup#export-zephyr-core)
7. [Install Zephyr Python Dependencies](https://zmk.dev/docs/development/setup#install-zephyr-python-dependencies)
8. Build the firmware 
    ```
    west build -s zmk/app -b bt60_v2 -- -DZMK_CONFIG="$(pwd)/config"