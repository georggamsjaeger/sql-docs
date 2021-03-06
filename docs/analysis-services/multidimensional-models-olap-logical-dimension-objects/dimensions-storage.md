---
title: "Dimension Storage | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "analysis-services"
ms.prod_service: "analysis-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "pro-bi"
ms.technology: 
  - "analysis-services"
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "SQL Server 2016 Preview"
helpviewer_keywords: 
  - "dimensions [Analysis Services], storage"
  - "storing data [Analysis Services]"
  - "storage [Analysis Services], dimensions"
  - "relational OLAP"
  - "multidimensional OLAP"
  - "MOLAP"
  - "storing data [Analysis Services], dimensions"
  - "ROLAP"
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
caps.latest.revision: 31
author: "Minewiskan"
ms.author: "owend"
manager: "kfile"
ms.workload: "Inactive"
---
# Dimensions - Storage
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:  
  
-   Relational OLAP (ROLAP)  
  
-   Multidimensional OLAP (MOLAP)  
  
 The storage mode determines the location and form of a dimension's data. MOLAP is the default storage mode for dimensions. **Related topics:**[Partition Storage Modes and Processing](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
## MOLAP  
 Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. This multidimensional structure is created and populated when the dimension is processed. MOLAP dimensions provide better query performance than ROLAP dimensions.  
  
## ROLAP  
 Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension. The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance. Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.  
  
> [!IMPORTANT]  
>  If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube. Failure to do this may result in inconsistent results when querying the cube. **Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../../analysis-services/instances/automate-analysis-services-administrative-tasks-with-ssis.md).  
  
## See Also  
 [Partition Storage Modes and Processing](../../analysis-services/multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
