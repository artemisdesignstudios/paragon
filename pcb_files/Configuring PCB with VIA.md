# Configuring Your Paragon PCB with VIA

### 05.11.2023 Update:
- New hex files have been created for the Paragon PCBs which now provide support for customizing the encoder out of the box!

---

## Prerequisites:

- Install **QMK Toolbox** to flash the PCB.
    - [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) 
- USB C cable to connect the PCB to your device.

---

## Flashing the PCB

1. Download the appropriate hex file for your PCB.
    - **Solder:** [/via_files/paragon_solder_via.hex](/pcb_files/via_files/paragon_solder_via.hex)
    - **Hotswap:** [/via_files/paragon_hotswap_via.hex](/pcb_files/via_files/paragon_hotswap_via.hex)

2. Open QMK Toolbox. 

3. Set the PCB into **DFU mode.** 
**Note:** the PCB must be connected to your device to be set into DFU mode.
    - DFU mode can be enabled through the following methods:
        1. Press the `RESET` button, located on the back of the PCB near the JST connector.
        2. If you already built your PCB, hold down both `SHIFT` keys (left and right) and press `B`. 
            - **Note:** We do **NOT** recommend building your PCB without testing it first. 
    - QMK Toolbox will tell you if the PCB is in DFU mode with the following message: 
    
        ```
        Atmel DFU device connected: ATMEL ATm32U4DFU (03EB:2FF4:0000)
        ```

4. In QMK Toolbox, click `Open` and load the downloaded hex file for your PCB. 

5. Click `Flash`. A successful flash will provide the following message:

    ```
    Attempting to flash, please don't remove device
    > dfu-programmer atmega32u4 erase --force
    > Erasing flash...  Success
    > Checking memory from 0x0 to 0x6FFF...  Empty
    > dfu-programmer atmega32u4 flash --force /Users/<your_user>/Downloads/paragon_<PCB_type>_via.hex
    > 0%                            100%  Programming 0x5A80 bytes...
    > [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
    > 0%                            100%  Reading 0x7000 bytes...
    > [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
    > Validating...  Success
    > 0x5A80 bytes written into 0x7000 bytes memory (80.80%)
    > dfu-programmer atmega32u4 reset
    Flash complete
    Atmel DFU device disconnected: ATMEL ATm32U4DFU (03EB:2FF4:0000)
    ```

---

## Configuring your PCB through VIA

1. Download [paragon_via_config.json](/pcb_files/via_files/paragon_via_config.json) from our repository.

2. Go to the [VIA](https://usevia.app/) website.

3. Click the **Authorize** button and select `Paragon` from the pop-up dialogue that appears. Performing this action will not change the webpage.

4. Click on the **Settings** icon on the far left side of the header tab.

5. In the **Settings** tab, enable `Show Design tab`.

6. Click on the `Load` icon and select the `paragon_via_config.json` file you previously downloaded. Upon loading the file, VIA will ask you to authorize the Paragon PCB again.

7. You should now be able to head to the **Configure** tab and start manipulating the keymap for your PCB.

## Configuring the Encoder

1. To configure the behavior of the encoder, head over to the **Configure** tab in VIA.

2. Click on the **encoder button** located in the top right corner of the layout schematic.

3. Two options should appear:
    1. `Rotate Counterclockwise`
    2. `Rotate Clockwise`

    By default, the `Rotate Counterclockwise` setting will be set to `KC_VOLU` (volume up). The `Rotate Clockwise` setting will be set to `KC_VOLD` (volume down).

4. To change the settings, click on the field associated with the turn direction, and enter your desired QMK Keycode. A list of QMK Keycodes can be found here: https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md
    - Keycode Examples:
        - Brightness Up: `KC_BRIU`
        - Brightness Down: `KC_BRID`

