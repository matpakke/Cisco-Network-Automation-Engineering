## Traditional Network Management
 Network operations, as you know them, are based on human interaction with network devices. Commonly using text editors, network engineers build one device configuration at a time. Engineers may copy an existing configuration into a file and search their way through updating it for each new device. Once this archaic method of building configurations is complete, network engineers connect to devices using either the console, Telnet, or SSH, to copy and paste the configurations onto the devices. 

 ![Traditional Network Management](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ewyj5KfXTV6Mo-Sn171eGg_7b09ee372f3245a2bb9c73dc7777c2a1_CSAU_1-0-0_Operations_Management_001.png?expiry=1689552000000&hmac=3B5UYGzDIch9s4NN5mwj2lBYBYgbby48Ez58FA50-GU)

 This process poses several problems when working with networks of any shape and size. As you look back at how networks have been managed, consider the following:

- First, the CLI was designed for human interaction and limits the speed of configuration to the speed at which the user can work. 

- Second, manual configuration and common copying and pasting methods are extremely prone to error, especially when configuring multiple devices. 

- Third, tasks are not easily repeatable and result in suboptimal workflows. 

In the late 1980s, the industry developed an interface that was built for machine-to-machine communications to manage and monitor large networks in a standardized fashion. It was called the Simple Network Management Protocol (SNMP). Instead of an engineer connecting to each device and obtaining necessary information, a server, part of a network management system (NMS), performed this function through SNMP polling. The interface had another benefit: if something went wrong or an event occurred, the device notified the server using SNMP traps. Although SNMP can also configure devices to a certain degree, it is rarely used in that manner in production. SNMP has its issues as well, but it was a move in the right direction. 

Although SNMP has different properties, it is best known and used today to simply poll network devices for operational statuses such as interface up, interface down, memory utilization, CPU utilization, bandwidth utilization, and many other basic properties.