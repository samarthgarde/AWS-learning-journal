# 💾 EC2 Instance Storage

## EBS Elastic Block Store - Volumes

**Main Information about Elastic Block Store:**
- An EBS Volume is a network drive that you can attach to your instance while they run. It uses the network to communicate with the instance, so it might have a little bit of latency.
- It can be detached from an instance and attached to other quickly (benefit of network driver)

**Good to know about EBS:**
- Free tier: 30 GB of EBS on General Purpose (SSD) or Magnetic per Month.
- Analogy to a "network USB stick" that you can plug in other computers.

## EBS Snapshot
- Snapshot is a backup of our EBS Volumes at a point in time. It keeps available in one Region. But to use it in a volume, we need to create the volume inside an AZ.

## EC2 Instance Store
- This is the physical HARD DRIVE attached to the server. Limited space, but higher performance. It is called by ephemeral

## EFS - Elastic File System

EFS stands to Elastic File System and it is a Network File System (NFS). This NFS can be attached to hundreds of EC2 instances at a time.
- Amazon EFS is a regional service storing data within and across multiple Availability Zones (AZs) for high availability and durability.
- It is a shared NFS.

## EBS vs EFS

- EBS are bound to one AZ and can be attached to one instance at a time. To move across regions we can use the snapshots (it is just a copy).
- EFS works across multiple regions and can be attached to multiple instances. The same data is available to all instances. It makes the EFS a shared file system.

