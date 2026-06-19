# Azure Cost Report for Small Web Application

## Overview

This report provides a cost estimate for hosting a small web application on Microsoft Azure. The application requirements are:

* 2 vCPUs
* 4 GB RAM
* 100 GB storage
* 50 GB monthly outbound data transfer
* 24/7 availability (730 hours/month)

The estimate includes both Linux and Windows deployment scenarios and evaluates the impact of Azure Hybrid Benefit on Windows workloads.

---

# Application Specifications

| Resource              | Specification              |
| --------------------- | -------------------------- |
| Compute               | 2 vCPU, 4 GB RAM           |
| Storage               | 100 GB                     |
| Monthly Data Transfer | 50 GB                      |
| Availability          | Single-instance deployment |
| Operating System      | Linux and Windows          |

---

# Azure Services Selected

## Azure Virtual Machine

The application is hosted on an Azure Virtual Machine.

Selected Configuration:

| Configuration | Value           |
| ------------- | --------------- |
| VM Size       | Standard B2s    |
| vCPUs         | 2               |
| Memory        | 4 GiB           |
| Usage         | 730 hours/month |

---

# Linux Deployment Cost Estimate

## Compute

| Service      | Monthly Cost |
| ------------ | -----------: |
| B2s Linux VM |       $30.00 |

---

## Managed Disk

| Configuration | Value        |
| ------------- | ------------ |
| Disk Type     | Standard SSD |
| Capacity      | 128 GB       |

Estimated Cost:

| Service      | Monthly Cost |
| ------------ | -----------: |
| Managed Disk |        $5.50 |

---

## Azure Storage Account

Storage is used for backups, static files, and application assets.

| Configuration | Value        |
| ------------- | ------------ |
| Storage Type  | Blob Storage |
| Capacity      | 100 GB       |

Estimated Cost:

| Service         | Monthly Cost |
| --------------- | -----------: |
| Storage Account |        $2.00 |

---

## Public IP Address

| Service            | Monthly Cost |
| ------------------ | -----------: |
| Standard Public IP |        $3.00 |

---

## Data Transfer

| Configuration     | Value       |
| ----------------- | ----------- |
| Outbound Transfer | 50 GB/month |

Estimated Cost:

| Service       | Monthly Cost |
| ------------- | -----------: |
| Data Transfer |        $4.00 |

---

## Inter-Zone Networking

Assumption:

* 50 GB monthly Availability Zone traffic

Estimated Cost:

| Service            | Monthly Cost |
| ------------------ | -----------: |
| Inter-Zone Traffic |        $0.50 |

---

# Linux Monthly Cost Breakdown

| Service                  | Monthly Cost |
| ------------------------ | -----------: |
| B2s Linux VM             |       $30.00 |
| Managed Disk             |        $5.50 |
| Storage Account          |        $2.00 |
| Public IP                |        $3.00 |
| Data Transfer            |        $4.00 |
| Inter-Zone Traffic       |        $0.50 |
| **Total Estimated Cost** |   **$45.00** |

---

# Windows Deployment Cost Estimate

## Scenario A: Windows VM with Azure Hybrid Benefit

Azure Hybrid Benefit allows organizations to reuse existing Windows Server licenses, reducing Windows VM costs.

### Monthly Cost Breakdown

| Service                  | Monthly Cost |
| ------------------------ | -----------: |
| B2s Windows VM           |       $30.00 |
| Managed Disk             |        $5.50 |
| Storage Account          |        $2.00 |
| Public IP                |        $3.00 |
| Data Transfer            |        $4.00 |
| Inter-Zone Traffic       |        $0.50 |
| **Total Estimated Cost** |   **$45.00** |

---

## Scenario B: Windows VM without Azure Hybrid Benefit

Without Hybrid Benefit, Windows licensing costs are included in the VM price.

### Monthly Cost Breakdown

| Service                  | Monthly Cost |
| ------------------------ | -----------: |
| B2s Windows VM           |       $50.00 |
| Managed Disk             |        $5.50 |
| Storage Account          |        $2.00 |
| Public IP                |        $3.00 |
| Data Transfer            |        $4.00 |
| Inter-Zone Traffic       |        $0.50 |
| **Total Estimated Cost** |   **$65.00** |

---

# Azure Discount Options

## Azure Savings Plan for Compute

Azure Savings Plan allows customers to commit to a fixed hourly spend for one or three years.

Benefits:

* Flexible across VM families and regions
* Supports multiple Azure compute services
* Up to 65% savings compared to Pay-As-You-Go pricing

Suitable for:

* Dynamic workloads
* Growing environments

---

## Azure Reserved VM Instances

Reserved VM Instances provide discounts for committing to a specific VM configuration.

Benefits:

* Up to 72% savings
* Predictable monthly costs
* Ideal for stable workloads

Suitable for:

* Production environments
* Long-term deployments

---

## Azure Hybrid Benefit

Azure Hybrid Benefit provides additional savings for Windows workloads by allowing organizations to use existing Windows Server licenses in Azure.

Benefits:

* Reduced Windows VM licensing costs
* Can be combined with Savings Plans or Reserved Instances
* Significant savings for Microsoft-centric organizations

---

# Cost Optimization Recommendations

## 1. Use Azure Savings Plans or Reserved Instances

Organizations with predictable workloads should use commitment-based pricing models to reduce compute costs.

Expected Benefit:

* Up to 72% savings on virtual machine costs

---

## 2. Optimize Resource Utilization

Recommendations:

* Right-size virtual machines
* Shut down development and test environments when not in use
* Move infrequently accessed data to lower-cost storage tiers

Expected Benefit:

* 20–50% reduction in cloud spending

---

# Conclusion

The estimated monthly cost of hosting the small web application on Azure is:

| Deployment Type             | Monthly Cost |
| --------------------------- | -----------: |
| Linux VM                    |       $45.00 |
| Windows VM (Hybrid Benefit) |       $45.00 |
| Windows VM (Standard)       |       $65.00 |

Azure is particularly cost-effective for organizations that already use Microsoft technologies and can take advantage of Azure Hybrid Benefit. For Windows-based enterprise workloads, Azure often provides better overall value due to licensing savings and seamless integration with the Microsoft ecosystem.
