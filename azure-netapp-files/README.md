# ARM Template to Deploy Azure NetApp Files

## Prerequisites

- To use this ARM template, you have to [Registration for Azure NetApp Files and NetApp Resource Provider](https://docs.microsoft.com/en-us/azure/azure-netapp-files/azure-netapp-files-quickstart-set-up-account-create-volumes?tabs=azure-portal#register-for-azure-netapp-files-and-netapp-resource-provider)

## What Azure Resources were Deployed with This ARM Template

- A Virtual Network with 2 Subnets
    - one subnet to deploy Azure NetApp Files volume,
    - the other subnet was left empty
- A Network Security Group on subnet for VMs
    - Inbound traffic from `Internet` was `denied` while provisioning
- A Azure NetApp Files account, capacity pool and volume

## Parameters

- `vnetName`: name of Virtual Network to create.
- `vmNSGName`: name of Network Security Group to provision, and it will attach on subnet created for VMs.
- `vnetAddressSpace`: address spacing of Virtual Network (e.g., `192.168.100.0/24`)
- `vmSubnetName`: name of subnet in Virtual Network to provision VMs.
- `anfSubnetName`: name of usbnet in Virtual Network to provision Azure NetApp Files volume.
- `vmSubnetAddressPrefix`: address prefix for subnet to provision VMs (e.g., `192.168.100.0/25`)
- `anfSubnetAddressPrefix`: address prefix for subnet to provision Azure NetApp Files (e.g., `192.168.100.128/25`)
- `anfAccountName`: name of Azure NetApp Files account to deploy.
- `anfPoolName`: name of Azure NetApp Files capacity pool to deploy.
- `anfPoolTier`: performance tier of Azure NetApp Files account.
- `anfPoolSize`: size of Azure NetApp Files capacity pool in bytes, the allowed values are for 4TiB, 8TiB, 10TiB, 12TiB, 15TiB or 20TiB.
- `anfVolumeName`: name of Azure NetApp Files volume.
- `anfVolumeExportName`: name of Azure NetApp Files to export (i.e., the directory name to export for NFS client).
