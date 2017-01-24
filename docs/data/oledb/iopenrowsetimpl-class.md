---
title: "Класс IOpenRowsetImpl | Microsoft Docs"
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
  - "IOpenRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOpenRowsetImpl - класс"
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс IOpenRowsetImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает реализацию интерфейса `IOpenRowset`.  
  
## Синтаксис  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### Параметры  
 `SessionClass`  
 Класс, производный от `IOpenRowsetImpl`.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Создает объект набора строк.  Не вызывается непосредственно пользователем.|  
|[OpenRowset](../Topic/IOpenRowsetImpl::OpenRowset.md)|Открывает и возвращает набор строк, включающий все строки из одного базовой таблицы или индекса. \(Не в ATLDB.H\)|  
  
## Заметки  
 Интерфейс [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) необходим для объекта сеанса.  Он открывает и возвращает набор строк, включающий все строки из одного базовой таблицы или индекса.  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)