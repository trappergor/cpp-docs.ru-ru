---
title: "Класс CEnumeratorAccessor | Microsoft Docs"
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
  - "ATL::CEnumeratorAccessor"
  - "CEnumeratorAccessor"
  - "ATL.CEnumeratorAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumeratorAccessor - класс"
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CEnumeratorAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется [CEnumerator](../../data/oledb/cenumerator-class.md) для получения данных из набора строк перечислителя.  
  
## Синтаксис  
  
```  
class CEnumeratorAccessor  
```  
  
## Члены  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Переменная, указывающее, является ли перечислитель родительский перечислитель, если строка перечислитель.|  
|[m\_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Переменная, указывающее, содержит ли строка источника данных или перечислитель.|  
|[m\_szDescription](../Topic/CEnumeratorAccessor::m_szDescription.md)|Описание источника данных или перечислителя.|  
|[m\_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Имя источника данных или перечислителя.|  
|[m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Строка, которую требуется передать [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) для получения моникер для источника данных или перечислителя.|  
  
## Заметки  
 Этот набор строк содержит источников данных и для перечислителей из текущего перечислителя.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)