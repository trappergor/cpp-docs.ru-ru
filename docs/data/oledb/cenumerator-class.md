---
title: "Класс CEnumerator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CEnumerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumerator - класс"
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Класс CEnumerator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Использует объект перечислителя OLE DB, который предоставляет интерфейс [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) для получения набора строк, описывающих все источники данных и перечислителей.  
  
## Синтаксис  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Find](../Topic/CEnumerator::Find.md)|Поиск доступных поставщиков \(источники данных\) и одно с указанным именем.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Получает интерфейс `IMoniker` для текущей записи.|  
|[Откройте .](../Topic/CEnumerator::Open.md)|Будет открыт перечислитель.|  
  
## Заметки  
 Можно извлечь данные **ISourcesRowset** косвенно от этого класса.  
  
## Требования  
 **Header:** atldbcli.h  
  
## См. также  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)