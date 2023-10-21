# M365-Azure-Project-VirtualCompany-XYZ-Tech-Oy-
The objective of this project is to design and implement a virtual company's IT infrastructure using Microsoft 365 (M365) and Azure, simulating various aspects of system administration. The project aims to create a development environment that mirrors real-world scenarios and will be referred to as "XYZ Tech Oy."


Project Network Setup (Diagram):

                  Azure Firewall ()
                       |
           +-----------+-----------+
           |                       |
   +-------+-------+       +-------+-------+
   | RouterVM (Azure VM)     | Azure Bastion (if used)
   |                       |  (Public IP)
   | +---------------+     |
   | | Frontend NIC  |     |
   | |  - Private IP |     |
   | |  - 10.0.1.4   |     |
   | +---------------+     |
   |                       |
   | +---------------+     |
   | | Backend NIC  |     |
   | |  - Private IP |     |
   | |  - 10.0.2.4   |     |
   | +---------------+     |
   |                       |
   | +---------------------+
   | | Internal Firewall  |
   | | (e.g., Azure Firewall)|
   | +---------------------+
   |                       |
   | +---------------------+
   | | Custom Applications, |
   | | Services, or Resources|
   | | within Backend Subnet|
   | | (e.g., Web Servers,  |
   | | Databases)          |
   | +---------------------+
   |                       |
   |                       |
   +-----------------------+
           |               |
   +-------+-----+   +-----+-------+
   | Frontend   |   | Backend    |
   | Subnet     |   | Subnet     |
   | (10.0.1.0/24) | (10.0.2.0/24) |
   |             |   |             |
   | +---------+ |   | +---------+ |
   | | Azure   | |   | | Custom  | |
   | | Bastion | |   | | Apps or | |
   | | Host    | |   | | Services| |
   | +---------+ |   | +---------+ |
   |             |   |             |
   +-------------+   +-------------+
                       |
           +-----------+-----------+
           | TestSubnet (10.0.3.0/24) [If used]
           | +-----------------+
           | | TestClientVM  |
           | | (10.0.3.4)    |
           | +-----------------+
