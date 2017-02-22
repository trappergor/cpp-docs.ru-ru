---
title: "Класс IConvertTypeImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IConvertTypeImpl<T>"
  - "IConvertTypeImpl"
  - "ATL.IConvertTypeImpl"
  - "ATL::IConvertTypeImpl"
  - "ATL::IConvertTypeImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IConvertTypeImpl - класс"
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс IConvertTypeImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию интерфейса [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx).  
  
## Синтаксис  
  
```  
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IConvertTypeImpl`.  
  
## Члены  
  
### Методы Interface  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|Предоставляет сведения о доступности преобразований типов в команде или в наборе строк.|  
  
## Заметки  
 Этот интерфейс используется в командах, наборов строк и наборах строк индекса.  **IConvertTypeImpl**  реализует интерфейс, делегировать для преобразования, предоставленный объект OLE DB.  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)