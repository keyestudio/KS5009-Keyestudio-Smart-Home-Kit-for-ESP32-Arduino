# Get started with Arduino


**1. Windows System**

![](media/6cf6312dc7c7db27794b54d58a8bf80c.png)

**1.1 Installing Arduino IDE**

When you get control board, you need to download Arduino IDE and driver
firstly.

You could download Arduino IDE from the official website:

<https://www.arduino.cc/>, click the **SOFTWARE** on the browse bar,
then click“DOWNLOADS” to enter download page, as shown below:

![](media/bfe8c9e405c71123dee7921eddff86d3.png)

![](media/7250961db41ba42e4b881d77bd76a319.png)

There are various versions of IDE for Arduino. Just download a version
compatible with your system. Here we will show you how to download and
install the windows version of Arduino IDE.

![](media/894116c5cf0023dd9720946cfb441790.png)

There are two versions of IDE for WINDOWS system. You can choose between
the installer (.exe) and the Zip file. For installer, it can be directly
downloaded, without the need of installing it manually while for Zip
package, you will need to install the driver manually.

![](media/a983a2f2eceb968afbff8ba0f0376240.png)

You just need to click JUST DOWNLOAD.

After the Arduino is downloaded, click“I Agree”to continue installing

![](media/00e334d3c756a2495da6f0d1b2db680a.png)

Click **Next**

![](media/de541d90a1cda992ad8e3f0cbaf95f94.png)

Then click **Install.**

![](media/7da9aca1e8432c59372e7c7ab2574bd9.png)

If the following page appears, click **Install.**

![](media/85b29de2aa791ecc77280ccde91e53c5.png)

![](media/739c41701fbcab202f0e587f534bad30.png)

![](media/d28223c55a30f949760779720fe4ec24.png)

**1.2 Install a driver**

If you have installed the CH340 driver, just skip it.

Connect the main control board to your computer with a USB cable, and
the driver will be installed automatically on MacOS and Windows10
system. If the driver installation process fails, you need to install
the driver manually.

(1) Check whether the computer automatically installs the driver:

Right click Computer----- Click Properties-----Click Device Manager, the
following picture shows the successful installation:

![](media/789a5b530a3e6c44687099a219575666.png)

(2) Manual installation:  

Right-click “**USB2.0-Serial**” and click “**Update drive...**”

![](media/378b65e69d5a926721245ecb4d2209a7.png)

Click “**Browse my computer for driver software**”

![](media/dc27c46ecc96141df0ff60cf605875f3.png)

Click“**Browse...**”and select the“**usb\_ch341\_3.1.2009.06 folder**”.

![](media/07a14dfc5fe0a81c53bcd633f94297da.png)

Check the serial port connection status again, as shown in the following
figure, the driver is successfully installed.

![](media/789a5b530a3e6c44687099a219575666.png)  

**1.3. Arduino IDE Setting**

![](media/71a8ae24d0cdf917006be05e8b885c77.png)

A- Used to verify whether there is any compiling mistakes or not.

B- Used to upload the sketch to your Arduino board.

C- Used to create shortcut window of a new sketch.

D- Used to directly open an example sketch.

E- Used to save the sketch.

F- Used to send the serial data received from board to the serial
monitor.

**1.4. Start your first program**

（1）Click“**File**”, select“**Examples**”，select the **"Blink"** in the
first file **"Basics" .**

![](media/7fc7ec495ec766ca7a442524966e2597.png)

![](media/1af9a17e6f268c33ed6d8c125f3566c9.png)

(2) Select the correct mainboard and serial port

![](media/314a7eededde4555897fc2accc01609c.png)

(3) Click ![](media/9c9158a5d49baa740ea2f0048f655017.png)icon to upload the code successfully.

![](media/0245a7fb9e4c27c752c100a1e64c7f28.png)

(4) Example test result:

You can see the LED lights flashing on the main control board.  

2.  **Mac System**

![](media/a6fc83596009c574d8e29ef383748549.png)

**2.1. Download Arduino IDE**

![](media/5a66fd8687ef293b9f655316a3bb49f1.png)

**2.2. Download the CH340 driver：**

<https://fs.keyestudio.com/CH340-MAC>

**2.3. How to install the CH340 driver：**

Please refer to the link ：

<https://wiki.keyestudio.com/Download_CH340_Driver_on_MAC_System>

**2.4. Arduino IDE Setting:**

Except for COM ports, the setting method is the same as in chapter 1.4:

![](media/a32ee0bad50ecd0883e381ec370a65f0.jpeg)

3.  **Add the ESP32 Environment**

（1）Open the arduino IDE，click File \> Preferences，as shown below:

![](media/7c420a8373645604cac519edd1471ac9.png)

（2）Copy the link：

<https://dl.espressif.com/dl/package_esp32_index.json>

（3）Open the button marked below:

![](media/86e9f22c59629bf4e9dda1c425598428.png)

(4) Paste it inside and click OK, as shown below

![](media/9c293e5bda22374594d5a7f42dca1aeb.png)

5)  Click Tools \> Board \> Boards Manager

![](media/53b7a340b28ad1b14a92cca7ac2474da.png)

6)  Find the ESP32 from the pop up Boards Manager and then click
    install.
    
    ![](media/aa2c23ae9e912e26d29317d7382de3b9.png)

7)  Click Tools \> Board to see the ESP32 Arduino
    
    ![](media/05471b0283825f3bf599d93e8bcd6085.png)

<!-- end list -->

4.  **Add Libraries**
    
    The library files provided are stored in the 1. Get started with
    Arduino \> Arduino Libraries file，as shown below；

![](media/6d63a49233f12bee21d6d884c02dcbe7.png)

**4.1 Method for Adding library Files in Windows**

(1) Open the Libraries folder in the Installation directory of the
Arduino IDE, as shown below:

Select and click ![](media/e22a310fcd1f734466f2bdcfd5a60fb5.png) and tap
![](media/948bd259f51aeeef7ec37b438283c3e9.png)to install the directory, then enter the
libraries file.

![](media/19a5d94b54e1045a6ba6887e8eb370bc.png)

(2) Copy all provided library file packages and paste the library files
into the Arduino IDE libraries folder opened in the previous steps.  

![](media/1806ee0bfc7aee1f72c5a324d170640f.png)

（3）Unzip the library file packages one by one.  

![](media/99dc25171e0d2c6626fb8fd73636365b.png)

**4.2 Method for Adding library Files in MacOS**

Choose Sketch \> Include Library \> Add.zip Library  

![](media/426c61c5f158b0fc6077e8d3728f6a69.png)

Find the library files and open them. You can only add them one by one,
as shown below:

![](media/6d63a49233f12bee21d6d884c02dcbe7.png)

 The installation is finished.
