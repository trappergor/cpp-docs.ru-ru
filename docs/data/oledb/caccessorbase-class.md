---
title: "Класс CAccessorBase | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorBase - класс"
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CAccessorBase
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Все методы доступа в шаблонах OLE DB являются производными от этого класса.  `CAccessorBase` позволяет один набор строк для управления несколько методов доступа.  Он также предоставляет привязку, как для параметров, так и для выходных столбцов.  
  
## Синтаксис  
  
```  
// Replace with syntax  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Закрыть](../../data/oledb/caccessorbase-close.md)|Закрывает доступ.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Извлекает маркер доступа.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Извлекает число доступа, созданных классом.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Тесты, совпадает ли указанный объект доступа автоматическим.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Выпуски доступ.|  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)