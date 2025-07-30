# 💻 Elastic Load Balancing and Auto Scaling Groups

## Scalability vs Elasticity (vs Agility)

- **Scalability:** is the ability for a system to accommodate a larger load by making the hardware stronger (vertical scale, scale-up) or by add nodes (horizontal scale, scale-out).

- **Elasticity:** Once the system is scalable, elasticity means that there will be some "auto-scaling" so that system can scale based on the load. This is "cloud-friendly": pay-per-use, match demand, optimize costs.

- **Agility**:not related to scale - distractor), new IT resources available very quickly. (one click away, what used to happen in weeks)

## Elastic Load Balancer (ELB)
Elastic Load Balancer are managed by AWS and they are servers that forward the internet traffic to multiple servers (EC2 Instances). They are the backend of EC2 Instances.

Why use a Load Balancer?
- Spread the load across multiple downstream instances.
- Expose a single point of access (DNS) to our application.

Why use an Elastic Load Balancer?
- AWS maintains and guarantees that it will be working
- AWS takes care of upgrades, maintenance, high availability

## Four Types of ELB
- Application Load Balancer: (HTTP/HTTPS only) - Layer 7
- Network Load Balancer: (Ultra-high performance, allows TCP) - Layer 4 (handle with millions of request per second, like gaming situation).
- Gateway Load Balancer: New AWS ELB used when you need to deploy and manage a fleet of third-party virtual appliances that support GENEVE
- Classic Load Balancer: (slowly retiring) - Layer 4 and 7

# Auto Scaling Groups (ASG)
The loads and access of websites can change overtime, so we need to add or remove resources. We can do it automatically by using the Auto Scaling Groups. 
- The main goal of ASG:
- Scale Out (add EC2 instances) to match an increased load.
- Scale In (remove EC2 instances) to match a decreased load.

## Scaling Strategies
**Manual Scaling**: We change manually in the console/cli the desired capacity of our ASG.

**Dynamic Scaling**: Respond to changing demand. We have four types of dynamic scaling strategies.
