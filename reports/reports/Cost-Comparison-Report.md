# AWS vs Azure Cost Comparison Report

## Executive Summary

This report compares the estimated monthly cost of hosting a small web application on Amazon Web Services (AWS) and Microsoft Azure. The application requires:

* 2 vCPUs
* 4 GB RAM
* 100 GB storage
* 50 GB monthly outbound data transfer
* 24/7 availability

The objective is to determine the most cost-effective cloud provider for different business scenarios and identify optimization opportunities.

---

# Application Specifications

| Resource        | Requirement        |
| --------------- | ------------------ |
| Compute         | 2 vCPU, 4 GB RAM   |
| Storage         | 100 GB             |
| Data Transfer   | 50 GB/month        |
| Availability    | 730 hours/month    |
| Deployment Type | Single VM Instance |

---

# Cost Comparison

## AWS Monthly Cost Estimate

| Service             | Cost (USD) |
| ------------------- | ---------: |
| EC2 t3.medium       |     $30.37 |
| EBS Storage         |      $2.40 |
| S3 Storage          |      $2.50 |
| Data Transfer       |      $4.50 |
| Inter-AZ Networking |      $1.00 |
| **Total**           | **$40.77** |

---

## Azure Linux Monthly Cost Estimate

| Service               | Cost (USD) |
| --------------------- | ---------: |
| B2s Linux VM          |     $30.00 |
| Managed Disk          |      $5.50 |
| Storage Account       |      $2.00 |
| Public IP             |      $3.00 |
| Data Transfer         |      $4.00 |
| Inter-Zone Networking |      $0.50 |
| **Total**             | **$45.00** |

---

## Azure Windows Monthly Cost Estimate

### With Azure Hybrid Benefit

| Service               | Cost (USD) |
| --------------------- | ---------: |
| B2s Windows VM        |     $30.00 |
| Managed Disk          |      $5.50 |
| Storage Account       |      $2.00 |
| Public IP             |      $3.00 |
| Data Transfer         |      $4.00 |
| Inter-Zone Networking |      $0.50 |
| **Total**             | **$45.00** |

### Without Azure Hybrid Benefit

| Service               | Cost (USD) |
| --------------------- | ---------: |
| B2s Windows VM        |     $50.00 |
| Managed Disk          |      $5.50 |
| Storage Account       |      $2.00 |
| Public IP             |      $3.00 |
| Data Transfer         |      $4.00 |
| Inter-Zone Networking |      $0.50 |
| **Total**             | **$65.00** |

---

# Price Difference Analysis

| Comparison                               |            Difference |
| ---------------------------------------- | --------------------: |
| AWS vs Azure Linux                       |  AWS cheaper by $4.23 |
| AWS vs Azure Windows (Hybrid Benefit)    |  AWS cheaper by $4.23 |
| AWS vs Azure Windows (No Hybrid Benefit) | AWS cheaper by $24.23 |

### Key Findings

* AWS provides the lowest estimated monthly cost for Linux-based deployments.
* Azure Linux costs are slightly higher but remain competitive.
* Azure Hybrid Benefit significantly reduces Windows licensing expenses.
* Without Hybrid Benefit, Windows workloads are substantially more expensive on Azure.

---

# Networking Cost Comparison

## Inter-Zone Data Transfer

| Provider | Monthly Cost (50 GB) |
| -------- | -------------------: |
| AWS      |                $1.00 |
| Azure    |                $0.50 |

### Analysis

AWS charges for cross-Availability Zone traffic in both directions, resulting in higher networking costs for distributed workloads.

Azure generally incurs lower inter-zone networking costs, making it more attractive for applications that rely heavily on communication between resources in different Availability Zones.

---

# Discount Mechanism Comparison

## AWS

### Savings Plans

* Commitment term: 1 year or 3 years
* Flexible across compute services
* Up to 66% savings

### Reserved Instances

* Commitment term: 1 year or 3 years
* Specific instance commitment
* Up to 72% savings

---

## Azure

### Azure Savings Plan

* Commitment term: 1 year or 3 years
* Flexible across compute services
* Up to 65% savings

### Reserved VM Instances

* Commitment term: 1 year or 3 years
* Specific VM commitment
* Up to 72% savings

### Azure Hybrid Benefit

* Reuse existing Windows Server licenses
* Reduces Windows VM licensing costs
* Can be combined with Savings Plans or Reserved Instances

---

# Cost-Effectiveness by Business Scenario

## Scenario 1: Linux-Based Startup

### Recommended Provider: AWS

Reasons:

* Lowest overall monthly cost
* Strong support for open-source technologies
* Mature cloud-native ecosystem
* Flexible pricing options

Estimated Monthly Cost:

```text
AWS: $40.77
Azure Linux: $45.00
```

---

## Scenario 2: Microsoft-Centric Enterprise

### Recommended Provider: Azure

Reasons:

* Azure Hybrid Benefit reduces Windows licensing costs
* Native integration with Microsoft technologies
* Better alignment with existing enterprise infrastructure

Estimated Monthly Cost:

```text
Azure Windows (Hybrid Benefit): $45.00
Azure Windows (Standard): $65.00
```

---

## Scenario 3: Long-Term Stable Production Workloads

### Recommended Approach

Either provider can be cost-effective when Reserved Instances or Reservations are used.

Organizations should select the provider that aligns best with their technology stack and operational requirements.

---

# Cost Optimization Strategies

## Strategy 1: Commitment-Based Discounts

### AWS

Use Savings Plans or Reserved Instances.

Potential Savings:

* 30–72%

### Azure

Use Azure Savings Plan or Reserved VM Instances.

Potential Savings:

* Up to 72%

Benefits:

* Lower compute costs
* Predictable budgeting
* Improved long-term cost efficiency

---

## Strategy 2: Resource Optimization

Recommendations:

* Right-size virtual machines
* Monitor resource utilization
* Schedule non-production workloads to shut down during off-hours
* Move infrequently accessed data to lower-cost storage tiers

Potential Savings:

* 20–50%

Benefits:

* Eliminates overprovisioning
* Reduces waste
* Improves overall cloud efficiency

---

# Final Recommendation

For the specified small web application:

### Choose AWS if:

* The application is Linux-based.
* Cost minimization is the primary objective.
* The organization prefers open-source technologies and cloud-native services.

### Choose Azure if:

* The organization uses Microsoft technologies extensively.
* Windows Server workloads are required.
* Azure Hybrid Benefit can be utilized.

Overall, AWS provides the lowest estimated monthly cost for Linux workloads, while Azure delivers strong value for Windows-based enterprise environments when licensing benefits are available. Both platforms offer significant cost reductions through commitment-based pricing models and resource optimization practices.
