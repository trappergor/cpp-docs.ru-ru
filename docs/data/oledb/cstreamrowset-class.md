---
title: "Класс CStreamRowset | Microsoft Docs"
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
  - "ATL::CStreamRowset<TAccessor>"
  - "ATL::CStreamRowset"
  - "CStreamRowset"
  - "ATL.CStreamRowset<TAccessor>"
  - "ATL.CStreamRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset - класс"
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CStreamRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется в объявлении `CCommand` или `CTable`.  
  
## Синтаксис  
  
```  
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### Параметры  
 `TAccessor`  
 Класс доступа.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Конструктор.  Создает и инициализирует объект `CStreamRowset`.|  
|[Закрыть](../../data/oledb/cstreamrowset-close.md)|Выпуски указатель интерфейса [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) в классе.|  
  
## Заметки  
 Используйте `CStreamRowset` в объявлении `CCommand` или `CTable`, например:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/CPP/cstreamrowset-class_1.cpp)]  
  
 или  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/CPP/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` возвращает указатель `ISequentialStream`, который хранится в `m_spStream`.  Затем используется метод **Чтение**, чтобы получить данные \(строки юникод\) в формате XML.  Примеры.  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/CPP/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 выполняет форматирование XML и возвращает все столбцы и строки набора как одну строку XML.  
  
> [!NOTE]
>  Эта функция работает только с SQL Server 2000.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)