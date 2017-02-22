---
title: "Класс IGetDataSourceImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IGetDataSourceImpl"
  - "ATL.IGetDataSourceImpl<T>"
  - "ATL.IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl"
  - "ATL::IGetDataSourceImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IGetDataSourceImpl - класс"
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс IGetDataSourceImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию объекта [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx).  
  
## Синтаксис  
  
```  
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IGetDataSourceImpl`.  
  
## Члены  
  
### Методы Interface  
  
|||  
|-|-|  
|[GetDataSource](../Topic/IGetDataSourceImpl::GetDataSource.md)|Возвращает указатель интерфейса объекта источника данных, который создал сеанс.|  
  
## Заметки  
 Это обязательный интерфейс в сеансе для получения указателя интерфейса к объекту источника данных.  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)