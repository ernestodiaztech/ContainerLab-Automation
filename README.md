# Network Automation - GitOps Workflow

Network automation repository using GitOps principles with ContainerLab, Ansible, and NetBox.

## Architecture

- **ContainerLab (10.33.99.12)**: Virtual network lab
- **Ansible (10.33.99.13)**: Automation control node
- **NetBox (10.33.99.14)**: Source of truth (IPAM/DCIM)

## Devices

| Device | Role   | Management IP   | Data IP      |
|--------|--------|-----------------|--------------|
| r1     | Router | 172.20.20.11/24 | 10.1.1.1/24  |
| r2     | Router | 172.20.20.12/24 | 10.1.2.1/24  |
| sw1    | Switch | 172.20.20.13/24 | -            |
| host1  | Host   | 172.20.20.14/24 | 10.1.100.1/24|

## CI/CD Pipeline
```mermaid
graph LR
    A[Git Push] --> B[Validation]
    B --> C[Testing]
    C --> D[Deployment]
    D --> E[Verification]
