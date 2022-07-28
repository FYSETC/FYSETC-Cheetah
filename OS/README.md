# OS

## SAMFi-OS_OrangePi_zero

Before you config the SAMF-OS_OrangePi_zero. You need an TF card with at least 8G capacity.

### Step 1

Download and flash the OS image with `balenaEtcher` software to your TF card. Insert your flashed TF card to OrangePi-zero and connect Ethernet cable then power on. Find the ip address of OrangePi-zero on your router, host name is `orangepizero`.

![](Orangepi-zero/orangepi_zero.jpg)

### Step 2

You can find the firmware `klipper.bin` in `Orangepi-zero` folder after you download the github repository. It is also stay in the OS path `firmwares\cheetah1.2.bin` after you login the OS with SSH.

Original SSH account and password:

```
account: fysetc
password: fysetc123
```

Flash the firmware with the command below after you connect your OrangePi and Cheetah with USB cable.

```
stm32flash -w firmwares/cheetah1.2.bin -v -i rts,-dtr,dtr /dev/ttyUSB0
```

Or follow the instructions [here](https://github.com/FYSETC/FYSETC-Cheetah#53-upload-the-firmware) for firmware uploading.

![](Orangepi-zero/cheetah.jpg)

### Step 3:

Prepare the `pinter.cfg`, using the command below

```
cp klipper_config/cheetah1.2.cfg firmware/printer.cfg
```

You probably need to change `id` by `ls /dev/serial/by-id` command.

I use the generic klipper config for this example, you need to change the config according to your machine. Now visit the webpage with your orangepi-zero IP address. Good to go.
