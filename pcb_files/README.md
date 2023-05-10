# Configuring Your Paragon PCB

## Prerequisites:

- Install **QMK Toolbox** to flash the PCB.
    - [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) 
- USB C cable to connect the PCB to your device.

---

## Flashing the PCB

1. Download the appropriate hex file for your PCB.
    - **Solder:** [paragon_solder.hex](paragon_solder.hex)
    - **Hotswap:** [paragon_hotswap.hex](paragon_hotswap.hex)

2. Open QMK Toolbox. 

3. Set the PCB into DFU mode. **Note:** the PCB must be connected to your device to be set into DFU mode.
    - DFU mode can be enabled through the following methods:
        1. Press the `RESET` button, located on the back of the PCB near the spacebar.
        2. If you already built your PCB, hold down both `SHIFT` keys (left and right) and press `B`. 
            - **Note:** We do **NOT** recommend building your PCB without testing it first. 
    - QMK Toolbox will tell you if the PCB is in DFU mode with the following message: 
    
        ```
        HID console connected: jtallbean Paragon (4A54:0001:0001)
        HID console disconnected: jtallbean Paragon (4A54:0001:0001)
        Atmel DFU device connected: ATMEL ATm32U4DFU (03EB:2FF4:0000)
        ```

4. In QMK Toolbox, click `Open` and load the downloaded hex file for your PCB. 

5. Click `Flash`. A successful flash will provide the following message:

    ```
    Attempting to flash, please don't remove device
    > dfu-programmer atmega32u4 erase --force
    > Erasing flash...  Success
    > Checking memory from 0x0 to 0x6FFF...  Empty
    > dfu-programmer atmega32u4 flash --force /Users/<your_user>/Downloads/paragon_<pcb_type>.hex
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

1. Download [paragon_via.json](paragon_via.json) from our repository.

2. Go to the [VIA](https://usevia.app/) website.

3. Click the **Authorize** button and select `Paragon - Paired` from the pop-up dialogue that appears. At this point, you should see no change in the webpage.

4. Click on the **Settings** icon on the far left of the header tab.

5. In the **Settings** tab, enable `Show Design tab`.

6. In the newly revealed **Design** tab, enable `Use V2 definitions (deprecated)`.

7. Click on `Load Draft Definiton` and select the `paragon_via.json` file you previously downloaded. Upon loading the file, VIA will ask you to authorize the Paragon PCB again.

8. You should now be able to head to the **Configure** tab and start manipulating the keymap for your PCB.

## Configuring the Encoder

At this point, we are currently ironing out an issue with configuring the rotary encoder. We aim to update this functionality ASAP. The default functionality of the rotary encoder is to change the brightness of your device.

