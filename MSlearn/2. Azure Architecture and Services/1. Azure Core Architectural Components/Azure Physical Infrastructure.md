With Microsoft Azure, you'll hear and use terms like **Regions, Availability Zones, Resources, Subscriptions and more.** The core architectural components of Azure may be broken down into two main groupings: the physical infrastructure and the management infrastructure.

- ### Physical Infrastructure:
	For Azure this starts with datacenters. Conceptually, the datacenters are the same as large corporate datacenters. They're facilities with resources arranged in racks, with dedicated power, cooling and network infrastructure. 
	
	As a global cloud provider, Azure has datacenters around the world. However, these individual datacenters aren't directly accessible.  Datacenters are grouped into **Azure Regions or Azure Availability Zones** that are designed to help you achieve resiliency and reliability for your business-critical workloads.

	- #### Regions:
		A region is a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network. Azure intelligently assigns and controls the resources within each region to ensure workloads and balance.
	
	- #### Availability Zones:
		Availability Zones are physically separate datacenters within an **Azure Region**. Each zone is made up of one or more datacenters equipped with independent power, cooling and networking. An availability zone is set up to be an isolation boundary. If one zone goes down, the other continues working. These zones are connected through high-speed, private fiber-optic networks.
			![Diagram showing three datacenters connected in a single Azure region representing an availability zone.](https://learn.microsoft.com/en-us/training/wwl-azure/describe-core-architectural-components-of-azure/media/availability-zones-c22f95a3.png)

### Use Availability Zones in your Apps:
You want to ensure your services and data are redundant so you can protect your information in case of failure. When you host your infrastructure, setting up your own redundancy requires that you create duplicate hardware environments. Azure can help make your app highly available through availability zones.

You can use availability zones to run mission-critical applications and build high-availability into your application architecture by co-locating your compute, storage, networking, and data resources within an availability zone and replicating in other availability zones. Keep in mind that there could be a cost to duplicating your services and transferring data between availability zones.

Availability zones are **primarily for VMs, managed disks, load balancers, and SQL databases.** Azure services that support availability zones fall into three categories:

- **Zonal services:** You pin the resource to a specific zone (for example, VMs, managed disks, IP addresses).
- **Zone-redundant services:** The platform replicates automatically across zones (for example, zone-redundant storage, SQL Database).
- **Non-regional services:** Services are always available from Azure geographies and are resilient to zone-wide outages as well as region-wide outages.

Even with the additional resiliency that availability zones provide, it’s possible that an event could be so large that it impacts multiple availability zones in a single region. To provide even further resilience, **Azure has Region Pairs**.

### Region Pairs:
Most Azure regions are paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away. This approach allows for the replication of resources across a geography that helps reduce the likelihood of interruptions because of events such as natural disasters, civil unrest, power outages, or physical network outages that affect an entire region. For example, if a region in a pair was affected by a natural disaster, services would automatically fail over to the other region in its region pair.

Examples of region pairs in Azure are West US paired with East US and South-East Asia paired with East Asia. Because the pair of regions are directly connected and far enough apart to be isolated from regional disasters, you can use them to provide reliable services and data redundancy.

![Diagram showing the relationship between geography, region pair, region, and availability zone.](https://learn.microsoft.com/en-us/training/wwl-azure/describe-core-architectural-components-of-azure/media/region-pairs-7c495a33.png)

- ### Additional advantages of region pairs:
	- If an extensive Azure outage occurs, one region out of every pair is prioritized to make sure at least one is restored as quickly as possible for applications hosted in that region pair.
	- Planned Azure updates are rolled out to paired regions one region at a time to minimize downtime and risk of application outage.
	- Data continues to reside within the same geography as its pair (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.