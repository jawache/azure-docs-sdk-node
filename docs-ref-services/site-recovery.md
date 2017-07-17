---
title: Azure Site Recovery module for Node.js
description: Reference for Azure Site Recovery module for Node.js
keywords: Azure,SDK,API,Site Recovery, Node.js
author: tomarcher
ms.author: tarcher
manager: douge
ms.date: 06/30/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: nodejs
ms.service: Site Recovery
---

# Azure Site Recovery Package for Node.js

## Overview

Site Recovery allows you to automate replication of Azure VMs between regions, on-premises virtual machines and physical servers to Azure, and on-premises machines to a secondary datacenter.

Learn more about [Azure Site Recovery](https://docs.microsoft.com/en-us/azure/site-recovery/site-recovery-overview).

## Management Package

### Install npm module
```bash
npm install azure-arm-recoveryservices
```

### Example

```javascript
const msRestAzure = require('ms-rest-azure');
const RecoveryServicesManagement = require('azure-arm-recoveryservices');

const subscriptionId = 'f7eef6d1-cb91-4ed4-813b-015b85228d35';
const resourceGroupName = 'jawache-node-web-1';

msRestAzure
  .interactiveLogin()
  .then(credentials => {
    const client = new RecoveryServicesManagement(credentials, subscriptionId);
    return client.vaults.listByResourceGroup(resourceGroupName);
  })
  .then(vaults => {
    console.log('List of vaults:');
    console.dir(vaults, { depth: null, colors: true });
  });
  
```

### Samples

Explore more [sample Node.js code](https://azure.microsoft.com/resources/samples/?platform=nodejs) you can use in your apps.
