When building or deploying a cloud application, two of the biggest considerations are uptime(Availability) and the ability to handle demand(Scalability).

- ### High Availability:
	Focuses on ensuring maximum availability, regardless of disruptions or events that may occur. When architecting a solution, we need to take account for service availability guarantees. Azure is a highly available cloud environment with uptime guarantees depending on the service. These guarantees are part of the Service-Level-Agreements(SLAs).

- ### Scalability:
	Scalability refers to the ability to adjust resources to meet demand. If you suddenly experience peak traffic and your systems are overwhelmed, the ability to scale means you can add more resources to better handle the increased demand.

	Because the cloud operates on a consumption-based model, you only pay for what you use. If demand drops off, you can reduce your resources and thereby reduce costs. This means you aren't overpaying for services.

	There are two varieties of scaling, **vertical and horizontal.** Vertical Scaling is focused on increasing or decreasing the capabilities of resources. Horizontal Scaling is adding or subtracting the number of resources.

	- **Vertical Scaling:**
		If you were developing an app and needed more processing power, you could vertically scale up to add more CPUs or RAM to the virtual machine. Conversely, if you realized you had over-specified the needs, you could vertically scale down by lowering the CPU or RAM specifications.

	- **Horizontal Scaling:**
		If you suddenly experienced a steep jump in demand, your deployed resources could be scaled out(automatically or manually). For example, you could add additional virtual machines or containers, scaling out. In the same manner, if there was a significant drop in demand, deployed resources could be scaled in(automatically or manually), scaling in.