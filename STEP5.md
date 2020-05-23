# Component #4: Reinvent the Net

Now is time for the final core component of this SDK. Let us start by accessing the source files:  
```
$ cd ../
$ cd Reinvent-the-Internet
$ unzip The APIs & Shell.zip
$ nautilus .
```  
Let us open the MSP430G2001.ccxml file with a text editor, i.e. “right click”:  
```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<configurations XML_version="1.2" id="configurations_0">
    <configuration XML_version="1.2" id="configuration_0">
        <instance XML_version="1.2" desc="TI MSP430 USB1" href="connections/TIMSP430-USB.xml" id="TI MSP430 USB1" xml="TIMSP430-USB.xml" xmlpath="connections"/>
        <connection XML_version="1.2" id="TI MSP430 USB1">
            <instance XML_version="1.2" href="drivers/msp430_emu.xml" id="drivers" xml="msp430_emu.xml" xmlpath="drivers"/>
            <platform XML_version="1.2" id="platform_0">
                <instance XML_version="1.2" desc="MSP430G2001" href="devices/MSP430G2001.xml" id="MSP430G2001" xml="MSP430G2001.xml" xmlpath="devices"/>
            </platform>
        </connection>
    </configuration>
</configurations>
```  
The fourth module (as one can tell), is hardware-oriented. The XML config shows that the driver is for a Texas Instruments dev board. This also means that the IDE that the fourth component was developed on was likely [CCS Cloud](https://dev.ti.com/).

Now you may be confused at this point as to what was the point of this module or what is it even for?

This part of the project was actually utilized for a hardware project in which somebody garnished underwater wireless signals through sonar conversion. However, similar use-cases can be done for anybody who wants to have a software defined network. This is your chance to expand the pipeline through low level hardware or code integrations and an optional part of the SDK.

To summarize we are:

 1. Offloading data
 2. Communicating Data
 3. Building our Blockchain
 4. Building our own SDN and wireless protocol

This is why things have been setup the way they are.
