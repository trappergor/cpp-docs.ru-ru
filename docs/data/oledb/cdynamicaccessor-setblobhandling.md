---
title: "CDynamicAccessor::SetBlobHandling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobHandling"
  - "CDynamicAccessor.SetBlobHandling"
  - "ATL::CDynamicAccessor::SetBlobHandling"
  - "SetBlobHandling"
  - "ATL.CDynamicAccessor.SetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobHandling - метод"
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ обработки значение для текущей строки.  
  
## Синтаксис  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### Параметры  
 `eBlobHandling`  
 Определяет, как данные больших двоичных объектов обрабатываться.  Он может принимать следующие значения:  
  
-   **DBBLOBHANDLING\_DEFAULT**: Обработка данных столбца больше `nBlobSize` \(в виде набора `SetBlobSizeLimit`\) как данные больших двоичных объектов и извлечь его через объект `ISequentialStream` или `IStream`.  Этот параметр пытается привязать каждый столбец, содержащий данные больше `nBlobSize` или представлены как **DBTYPE\_IUNKNOWN** как данные больших двоичных объектов.  
  
-   **DBBLOBHANDLING\_NOSTREAMS**: Обработка данных столбца больше `nBlobSize` \(в виде набора `SetBlobSizeLimit`\) как данные больших двоичных объектов и извлечь его через ссылку \(в выбранной, принадлежащей объект\-получатель памяти.  Этот параметр полезен для таблиц, в которых более одного столбца БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА и поставщик поддерживает только один объект `ISequentialStream` на доступ.  
  
-   **DBBLOBHANDLING\_SKIP**: Пропустите \(\) не выполняет привязку столбцов определяемого как содержать большие двоичные объекты \(доступ не привязывает или не извлекает значение столбца, но по\-прежнему содержит состояние и длина столбца\).  
  
## Заметки  
 Необходимо вызвать `SetBlobHandling` до вызова функции **Открыть**.  
  
 Метод [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) в конструкторе задает БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ обработки значение **DBBLOBHANDLING\_DEFAULT**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)