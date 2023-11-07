# PLC-Basic_ByDSD : Chapter-1 (Day 1)

## Install TIA Portal 18 and PLC Sim ADV 5.0
Fix IP Address at Network Connections (LAN card by Siemens PLCSIM Virtual Ethernet Adapter) (IP 192.168.0.104)

## Install Factory I/O
pass

## Setup Enviroment

### S7-PLCSIM Advanced V5.0
```
Select                      : TCP/IP
Select                      : Single Adapter
TCP/IP communication with   : Ethernet

Start Virtual S7-1500 PLC
Instance name       : PLC52
IP address [X1]     : 192.168.0.152
Subnet mask         : 255.255.255.0
Default gateway     : -
PLC family          : S7-1500
```

### TIA (Totally Integrated Automation)
```
Start               : set name --> Create
Devices & Networks  : Protection of confidential PLC data --> Choose NO Protects the PLC... --> Next
                    : Mode for PG/PC and HMI communication --> Choose No Only allow... (to be Lagacy)
                    : PLC access protection --> Access level without password : No access (complete protection)

Click : finish
```

Click : PROFINET interface_1
```
General     :   Interface networked with : Click "Add new subnet" (Subnet : PN/IE_1)
            :   Internet protocol version 4 (IPv4)

                Choose --> Set Ip address in the project
                IP address  : 192.168.0.152
                Subnet mask : 255.255.255.0

                Choose --> Use router
                Router address : 192.168.0.1
Click : Save
```

```
For Simulator : the project name --> right click at mouse --> Properties --> Protection --> Click : Support simulation ...

Click : Save
```

```
Double clice PLC interface

General : System and clock memory   :   System memory bits
                                        Click "Enable the use of system memory byte
                                        Address of system memory byte (MBx) : 10,000
                                    :   Clock memory bits
                                        Click "Enable the use of clock memory byte
                                        Address of system memory byte (MBx) : 15,000

        : Protection & Security     :   Connection mechanisms : Click "Permit access..."

Click : Save 
Click : Complier
```

### Connect TIA and S7-PLCSIM Advanced V5.0
At TIA
Click : Download to device --> Popup window "Extended download to device"
```
Type of PG/PC interface         :   PN/IE
PG/PC interface                 :   Siemens PLCSIM Virtual Ethernet Adapter
Connection to interface/subnet  :   Direct at slot '1 X 1'
Select target device            :   Show device with the same addresses
Click : Start search
Click : Load
Click : Connect

Load result 
Target : Start module --> Choose Action : Start module --> Click "Finish"

At S7-PLCSIM Advanced V5.0 --> Led for PLC52 is "Green"
```

## Programming
At PLC tags --> right click of mouse to click "add new tag table" and rename "MC1", Next, Import PLC tags.

