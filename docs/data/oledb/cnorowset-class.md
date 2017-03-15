---
title: "Класс CNoRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CNoRowset"
  - "ATL::CNoRowset<TAccessor>"
  - "CNoRowset"
  - "ATL.CNoRowset<TAccessor>"
  - "ATL::CNoRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoRowset - класс"
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Класс CNoRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Может использоваться в качестве аргумента шаблона \(`TRowset`\) для [CCommand](../../data/oledb/ccommand-class.md) или [CTable](../../data/oledb/ctable-class.md).  
  
## Синтаксис  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### Параметры  
 `TAccessor`  
 Класс доступа.  Значение по умолчанию — `CAccessorBase`.  
  
## Заметки  
 Используйте `CNoRowset` как аргумент шаблона, если команда не возвращает набор строк.  
  
 `CNoRowset` реализует следующие методы заглушки, каждый из которых соответствуют другим методам класса доступа.  
  
-   **BindFinished** — указывает, когда привязка результатов \(возвращает `S_OK`\).  
  
-   **Закрыть** — Строки выпусков и текущий интерфейс IRowset.  
  
-   `GetIID` — извлечение идентификатор интерфейса точки подключения.  
  
-   **GetInterface** — получает интерфейс.  
  
-   `GetInterfacePtr` — извлечение инкапсулированный указатель интерфейса.  
  
-   **SetAccessor** — получает указатель на доступ.  
  
-   **SetupOptionalRowsetInterfaces** — установка необязательные интерфейсы для набора строк.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)