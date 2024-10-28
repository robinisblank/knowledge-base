# Virtualization

## Understanding Virtualization
- Virtual Machines (VMs) are self-contained computers running on a host machine.
- Virtualization and emulation are two different concepts. In virtualization, we allocate some of our hardware to a separate internal system. It cannot do things that your hardware isn't capable of. In emulation, we pretend to have hardware that we don't have.
- To do virtualization, your CPU must be able to support it.
- You can enable/disable virtualization in system setup.
- A hypervisor is an actual host that runs VMs.
- A type 1 hypervisor runs directly on top of the hardware as an OS.
- A type 2 hypervisor runs as an application in an OS.
- Oracle VM VirtualBox is a very popular type 2 hypervisor.
- VMware ESXi, Microsoft Hyper-V, and KVM are some type 2 hypervisors.
- When you turn off a VM, it turns into a file that sits on your hard drive and you can turn it on whenever you want to.
- VMs can be used to run multiple websites on one powerful machine. This saves hardware costs and a lot of power.
- For security, VMs can be quickly shut down and backed up from an image file.
- VMs are great for sandbox testing and cross-platform virtualization.
- We don't get much efficiency when there's an OS between the hypervisor and the hardware. When we talk about robust hypervisors, we talk about type 1 hypervisors.
- We can create virtual networks using VMs.
- A VM is a guest OS that runs within a host OS. The hypervisor manages the guest OS and the interface between the guest OS and the shared hardware of the host OS.
- Virtual machines can be used to test OS or software patches before rolling them out company-wide. That way, if the patches introduce any problems, there's no harm done.

## Your First Virtual Machine
- Setting up a new VM takes a few steps:
	1. Install a hypervisor, like Oracle VirtualBox.
	2. Create a VM in the hypervisor.
	3. Download and install an OS, like Ubuntu Linux.
- The extension pack adds extra features to the base hypervisor.
- Different OSes have different resource requirements in VMs.
- VMs are also good for running legacy software and OSes (like Windows 7).
- RAM is the most important real estate when it comes to VMs. The more RAM you have, the more VMs you can run.

## Advanced Virtualization Setup
- Networking options in VirtualBox:
	- **Not Attached**: The VM has no network connection. It is completely isolated from other VMs, the host, and the Internet.
	- **Bridged Adapter**: The VM connects to the network through the host's physical network adapter. The VM gets its own MAC and IP address from the network's DHCP server, behaving like a separate machine on the same network as the host.
	- **NAT (Network Address Translation)**: The VM shares the host's IP address to access external networks like the Internet. The host acts as a virtual router. Multiple VMs can use NAT, but they are isolated from each other unless additional configuration (like port forwarding) is done. Use NAT to put a VM in a unique network ID.
	- **NAT Network**: Similar to NAT, but multiple VMs can connect to the same virtual network, allowing communication between them. The VMs share the same network ID and can access external networks through the host. Use NAT Network to put multiple VMs into a single network ID.
	- **Internal Network**: VMs can communicate only with each other on the same internal network. There is no connection to the host or external networks, making it useful for isolated network setups.
	- **Host-Only Adapter**: VMs can communicate with the host and other VMs using a virtual network interface, but they have no Internet or external network access. It’s useful for direct VM-to-host communication.
	- **Generic Driver**: Allows custom network setups using external drivers or specialized configurations like UDP tunnels. Typically used in advanced or experimental setups.
- Use VMs to practice with drives without purchasing any hardware, administrating different OSes, and virtual networking.
- Consider the same security best practices with VMs as you do with any other OS.

## Cloud Computing
- Cloud computing moves the VMs out onto a server somewhere, but makes them easily accessible through the Internet.
- Cloud computing enables rapid elasticity, on-demand scaling, and resource pooling.
- Rapid elasticity is the ability to quickly adjust resources to meet current demand.
- On-demand enables high availability, less downtime, and fewer crashes.
- Resource pooling allows sharing of resources like storage, memory, processing, and network bandwidth.
- Infrastructure as a Service (IaaS) provides virtualized computing resources over the Internet. For example: AWS EC2, Google Compute Engine.
- Platform as a Service (PaaS) offers a platform for developers to build, test, and deploy applications without managing the underlying infrastructure. For example: Heroku, Google App Engine.
- Software as a Service (SaaS) provides fully functional applications over the Internet. For example: Gmail, Microsoft 365, Dropbox.

## Cloud Ownership
- Private clouds are owned and used only by a single organization.
- Public clouds are privately owned but are available for public use, usually at a cost.
- Hybrid clouds have both private and public aspects.
- Community clouds are owned by multiple organizations for their own private use for cost sharing.

## Cloud-Based Applications
- Cloud storage enables access to synchronized saved files from any device.
- File synchronization can create a conflicted copy, save last made changes, or any other setting if multiple people access a file at the same time.
- Cloud-based applications move management to the Cloud for e-mail and more.
- Virtual desktops provide a consistent workspace in the Cloud that can be accessed from any device.
- Virtual application streaming provides access to apps without installing them locally.