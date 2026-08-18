## Practical: Create a VPC with Public and Private Subnets

### Objective

Create a custom AWS VPC with a public subnet and a private subnet, configure route tables, and connect the public subnet to the internet using an Internet Gateway.

### Architecture

```text
                    Internet
                       |
                Internet Gateway
                       |
                MyVPC - 10.0.0.0/16
                       |
          +------------+------------+
          |                         |
   Public Subnet              Private Subnet
    10.0.1.0/24                10.0.2.0/24
          |                         |
 Public Route Table          Private Route Table
          |                         |
  0.0.0.0/0 → IGW                 Local
```

### Step 1: Create the VPC

Created a custom VPC with the following configuration:

* **VPC Name:** `MyVPC`
* **IPv4 CIDR:** `10.0.0.0/16`

The VPC provides the main network range from which the subnet CIDR blocks are allocated.

### Step 2: Create Internet Gateway

Created an Internet Gateway:

* **Name:** `MyVPC-IGW`

Attached the Internet Gateway to `MyVPC`.

The Internet Gateway provides a path between the VPC and the internet.

### Step 3: Create Public Subnet

Created a public subnet:

* **Name:** `Public-Subnet`
* **IPv4 CIDR:** `10.0.1.0/24`

This subnet is intended for resources that need direct internet connectivity.

### Step 4: Create Private Subnet

Created a private subnet:

* **Name:** `Private-Subnet`
* **IPv4 CIDR:** `10.0.2.0/24`

This subnet does not have a direct route to the Internet Gateway.

### Step 5: Create Public Route Table

Created:

* **Name:** `Public-Route-Table`

Added the following routes:

| Destination   | Target           |
| ------------- | ---------------- |
| `10.0.0.0/16` | Local            |
| `0.0.0.0/0`   | Internet Gateway |

Associated the `Public-Subnet` with this route table.

The `0.0.0.0/0` route allows traffic from the public subnet to reach the internet through the Internet Gateway.

### Step 6: Create Private Route Table

Created:

* **Name:** `Private-Route-Table`

The route table contains the default local VPC route:

| Destination   | Target |
| ------------- | ------ |
| `10.0.0.0/16` | Local  |

Associated the `Private-Subnet` with this route table.

No Internet Gateway route was added to the private route table.

> NAT Gateway was not created because it incurs charges. This practical was designed to use only free VPC networking components.

### Final Configuration

```text
MyVPC
CIDR: 10.0.0.0/16

├── Public-Subnet
│   CIDR: 10.0.1.0/24
│   │
│   └── Public-Route-Table
│       ├── 10.0.0.0/16 → local
│       └── 0.0.0.0/0 → Internet Gateway
│
└── Private-Subnet
    CIDR: 10.0.2.0/24
    │
    └── Private-Route-Table
        └── 10.0.0.0/16 → local
```

### Practical Outcome

Successfully created and configured:

* Custom VPC
* Public subnet
* Private subnet
* Internet Gateway
* Public route table
* Private route table
* Route table associations
* Public subnet internet route

No NAT Gateway or other chargeable resources were created.
