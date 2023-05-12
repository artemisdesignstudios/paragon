# Configuring Your Paragon PCB with Vial

## Prerequisites:

- Install **QMK Toolbox** to flash the PCB.
    - [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) 
- USB C cable to connect the PCB to your device.

---

## Flashing the PCB

1. Download the appropriate hex file for your PCB.
    - **Solder:** [/vial_files/paragon_solder_vial.hex](/pcb_files/vial_files/paragon_solder_vial.hex)
    - **Hotswap:** [/vial_files/paragon_hotswap_vial.hex](/pcb_files/vial_files/paragon_hotswap_vial.hex)

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
    > dfu-programmer atmega32u4 flash --force /Users/<your_user>/Downloads/paragon_<PCB_type>_vial.hex
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

## Configuring your PCB through Vial

1. Head over to **[vial.rocks](https://www.vial.rocks)** with your PCB connected to your device.

2. Click on `Start Vial`. A list of connected devices should pop up.

3. Select `Paragon` from the device pop-up. At this point, the Vial UI should show up and display the layout schematic.


## Configuring the Encoder

1. To configure the behavior of the encoder in Vial, click on either of the **two encoder buttons** shown in the layout schematic.

2. The left-side encoder shows an icon of turning the encoder counterclockwise. The right-side encoder shows an icon of turning the encoder clockwise.

3. Clicking on either encoder button will allow you to map another function to it from the provided set.

