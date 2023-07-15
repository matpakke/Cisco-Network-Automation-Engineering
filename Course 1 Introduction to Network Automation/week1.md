## Traditional Network Management
 Network operations, as you know them, are based on human interaction with network devices. Commonly using text editors, network engineers build one device configuration at a time. Engineers may copy an existing configuration into a file and search their way through updating it for each new device. Once this archaic method of building configurations is complete, network engineers connect to devices using either the console, Telnet, or SSH, to copy and paste the configurations onto the devices. 

 ![Traditional Network Management](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ewyj5KfXTV6Mo-Sn171eGg_7b09ee372f3245a2bb9c73dc7777c2a1_CSAU_1-0-0_Operations_Management_001.png?expiry=1689552000000&hmac=3B5UYGzDIch9s4NN5mwj2lBYBYgbby48Ez58FA50-GU)

 This process poses several problems when working with networks of any shape and size. As you look back at how networks have been managed, consider the following:

- First, the CLI was designed for human interaction and limits the speed of configuration to the speed at which the user can work. 

- Second, manual configuration and common copying and pasting methods are extremely prone to error, especially when configuring multiple devices. 

- Third, tasks are not easily repeatable and result in suboptimal workflows. 

In the late 1980s, the industry developed an interface that was built for machine-to-machine communications to manage and monitor large networks in a standardized fashion. It was called the **Simple Network Management Protocol (SNMP)**. Instead of an engineer connecting to each device and obtaining necessary information, a server, part of a network management system (NMS), performed this function through SNMP polling. The interface had another benefit: if something went wrong or an event occurred, the device notified the server using SNMP traps. Although SNMP can also configure devices to a certain degree, it is rarely used in that manner in production. SNMP has its issues as well, but it was a move in the right direction. 

Although SNMP has different properties, it is best known and used today to simply poll network devices for operational statuses such as interface up, interface down, memory utilization, CPU utilization, bandwidth utilization, and many other basic properties.

---

# Scaling Network Management

With the CLI and SNMP as the dominant methods of network management, here is an example of how teams typically would scale: What do they do and how do they operate as the network continues to evolve? Even if networks are not expanding based on the number of routers and switches, in the past several years, additional devices and services have been increasing the size and complexity of the network: security, wireless, network fabric controllers, network overlays, and IPv6, to list just a few.  

![Scaling Network Management](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/Xrs5ATBFQRO7OQEwRVETHg_7073ab3c7ea74232b4a73934bd5a3da1_CSAU_1-0-0_Operations_Management_022.png?expiry=1689552000000&hmac=nHtUi6JX1oz2GViFd7pxKdUSOpgX1Zt2udpYgFQC1vU)

Imagine a company that has a small network with only a few network engineers. They can easily manage all nodes by just using CLI access. Over the course of a few years, the company has some growth and experiences more challenges in network operations. Now the network has more devices, which require more staff to support them. As the network scales, the major response historically has been to hire more network engineers. 

Although using the CLI should not be justifiable anymore, it has been the customary approach in the industry. However, there is a benefit of hiring more engineers—it creates skill-set diversity, which further highlights the issue. One new engineer might learn Python and another one learns Ansible. Although both of these tools help manage many devices at the same time, they also offer the ability to standardize and reduce human error. Each of these engineers improved their performance individually.

As time continues to go by, the network continues to expand and configurations are gradually added, which makes manual configuration management more difficult. Although it is more difficult to manage manually, each team member continues to do what they think is right for network automation. Some engineers use their own databases, some use Bash scripts, some use Perl scripts, some execute scripts from a server and store them in a git repository.

Although this is common, it does not benefit the network engineers and business. These tools are more than capable of managing the network, but there is no overall automation strategy. This mode of operation shows the value of automation and allows for some learned skills, but it should only be executed as a proof of concept (POC). Automating in production requires proper controls as part of a cohesive network management strategy.

---

# Practice Quiz for Traditional Network Management

**Question 1**: Which two statements best describe the current state of network operations? (Choose two.)

SSH and CLI are the primary means of network management.   

**Correct**
Most network operation teams still configure and manage their devices manually through the CLI, which can be accessed through a Console connection or over a network connection via SSH. 

SNMP is the primary programmatic interface for network management systems to communicate with network devices

**Correct**
Although many new network devices now offer APIs for network management, there are still many more legacy network devices in service that only support SNMP read and write access 

**Question 2**: What does a network operation team require in order to successfully benefit from network automation?

Network Operations teams need a cohesive network management strategy with proper controls and standards.

**Correct**
For network operations teams to be successful with network automation, they need a cohesive network management strategy. Without any direction or controls on how network automation will be handled can lead to technical gaps, miscommunications, and other adverse impacts that will make the network more difficult to handle.


**Question 3**: What is one reason why Simple Network Management Protocol (SNMP) is not an optimal protocol for programmatic network device configuration?

SNMP is not as reliable as other network configuration protocols.

**Correct**
SNMP has limited functionality compared to other more robust protocols used for network automation, such as NETCONF and RESTCONF. SNMP also has much more overhead compared to newer protocols, which can cause performance issues on network devices. SNMP can be more complex to understand and use, potentially leading to more errors when used in network automation.  These are some reasons that make SNMP a less reliable protocol for network automation compared to others.

---

# Network Automation and Programmability

There is currently a major industry shift away from the CLI as the primary way to interface with a network device. Network automation is taking shape with the rise of application programming interfaces (API)s that exist on network devices and software-defined network (SDN) controllers. Although the motto is “the API is the new CLI,” the truth is that the use of GUIs is diminishing too with the rise of APIs and automation.

![Network Automation](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/YxT0e5wbQOyU9HucG0DsqQ_b468124e2b764272afbc7077fbecdfa1_CSAU_1-0-0_Operations_CLI_001.png?expiry=1689552000000&hmac=0auE3AiJKwD7cMdmo9bwt-LeBAtvsJmZSbWPY72bSPk)

There are several important APIs and technologies that are used to create robust programmatic interfaces to network devices:

- Representational State Transfer (REST) APIs

- Network Configuration Protocol (NETCONF)

- REST Configuration Protocol (RESTCONF)

- "Yet Another Next Generation" (YANG) models (not an API, but a modeling language to create models that are used by the APIs)

- gRPC remote procedure call

The networking devices are the last pieces of the puzzle. They need to support one or more of the methods that were mentioned earlier to be easily adopted. Cisco is already on a mission to make every device API-enabled in every product family. You will find APIs on Cisco devices and on controller platforms like Cisco Application Policy Infrastructure Controller (APIC), Cisco DNA Center, and many more.

It is also worth mentioning that CLI is not going away anytime soon. It is a verified way to interact with network devices, and when advanced troubleshooting is required, it will be performed using CLI via SSH. When needed, network automation systems can also use SSH to communicate with network devices, especially when the device is older, or when the tool itself has not been updated to use a device’s API.


---

# Beyond APIs

The connection methods that need to be in place for machine-to-machine communication to happen, such as programmatic APIs on network devices, were discussed earlier. However, it is absolutely critical to understand that APIs are simply enablers. Although they are the foundation of next-generation automation, it is important to have a holistic view of operations and how those device APIs can be used within the life cycle of the network itsel       

![Beyond APIs](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/IxgVkMsTQciYFZDLE6HI6A_2a2c2383bcae441287df136ce215f2a1_CSAU_1-0-0_Operations_Operations_001.png?expiry=1689552000000&hmac=AfT5dMeXTfOqjU4TnlWwuT2PcE9vdwmLpLXW_8w94pg)

There are a few key trends that are emerging within the network industry, including development and operations (DevOps), Open Source, and the rise of automatable test infrastructure. 

- **DevOps**: DevOps is a cultural trend to promote and develop methods that improve speed and agility in the deployment, maintenance, and continual improvement of systems and infrastructure. It is important to understand that this cultural trend is driving better configuration and automation tools for network engineers. From within the DevOps movement, networking professionals can learn how applications, developers, and systems peers have been using DevOps tools including Git, Jenkins, Docker, Ansible, Salt, Puppet, and Chef, to name just a few.  

- **Open Source**: Within the DevOps movement, many of the tools are open source, but the companies that support the open-source projects offer commercial versions or support for the software. For example, although Git is open source, there are commercial offerings like GitHub, BitBucket, and GitLab. A benefit of the intersection of open source and DevOps as the foundation for next-generation operations is that it lowers the barrier to entry. Within minutes, you can have automation software installed and working in a lab environment. Open-source software could be a large project or something smaller in nature, like a software development kit (SDK), that makes it easier for you to build apps for the network. An SDK, a set of tools and often a wrapper around an API for networking, streamlines the consumption of a platform, product, and technology. 

- **Test Infrastructure**: Cisco Virtual Internet and Routing Lab (VIRL) and Cisco Modeling Labs are foundational components in automation because they enable testing. Although it is ideal to have a dedicated physical lab, it is sometimes cost-prohibitive. Using Cisco VIRL or Cisco Modeling Labs allow you to create devices virtually to perform automatic testing before deploying to production. 

As you progress on your network automation journey, keep in mind that you are concerned with more than an API or a single tool. You have the opportunity to rethink end-to-end network operations. These discussions will help you start to see the possibilities and even get a glimpse into software development pipelines and how they can be used for network operations.

---

# Cisco Network Automation and Programmability
Cisco has an extensive product portfolio, from core networking to the data center to the cloud, and from security to collaboration and now the Internet of Things (IoT).

![Cisco Products](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/lCI08ot8RTOiNPKLfAUzCA_87641d9a2eb74f939381461fa12f3fa1_CSAU_1-0-0_Operations_Programmability_001.png?expiry=1689552000000&hmac=uMuB66TOVryg4l0aOlSgYj3ZkpS53r3TE7EaMe6JqGE)

For years, Cisco has been working to ensure that every platform and every product that Cisco sells has an API to enable programmability and automation.

As you continue down the path of network automation, it is critical to keep an eye and ear open for high-value workflows that can be automated across technology silos and platforms. Each technology space often has its own team or silo within an enterprise, but it is the workflows and tasks that span teams that are the most valuable for the business. So even though you may not manage the firewalls or voice and collaboration systems, it is important to consider the impact of automating those systems as you interface with the security and collaboration teams, because they may not have the knowledge just yet.