---
title: Cultura de calidad
date: 2023-05-23
header:
  image: /assets/images/cover-images/1.png
  teaser: /assets/images/cover-images/1.png
categories:
  - Blog
tags:
  - Quality Enginner
  - Coaching
  - Testing
---

Aqui vamos a trabajar son la importancia de la calidad mas alla del testing.

```powershell

Connect-ServiceFabricCluster -ConnectionEndpoint <domain-without-https.com:19000> `
-KeepAliveIntervalInSec 10 -AzureActiveDirectory -ServerCertThumbprint <thumbprint>

$nodes = Get-ServiceFabricNode

For ($i = 0; $i -lt $nodes.Count; $i++) {

    $result =  Get-ServiceFabricDeployedReplica -NodeName $nodes[$i].NodeName -ApplicationName fabric:<appName> `
                | Where-Object ServiceName -eq fabric:<serviceName> | Select-Object -Property ReplicaId, Partitionid

    For ($j = 0; $j -lt $result.Count; $j++) {
        Write-Host $nodes[$i].NodeName $result[$j].Partitionid $result[$j].ReplicaId
        Restart-ServiceFabricReplica -NodeName  $nodes[$i].NodeName -PartitionId $result[$j].Partitionid -ReplicaOrInstanceId $result[$j].ReplicaId
    }
}

```
