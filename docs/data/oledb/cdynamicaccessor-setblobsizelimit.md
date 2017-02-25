---
title: "CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobSizeLimit"
  - "SetBlobSizeLimit"
  - "CDynamicAccessor.SetBlobSizeLimit"
  - "ATL.CDynamicAccessor.SetBlobSizeLimit"
  - "ATL::CDynamicAccessor::SetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobSizeLimit - метод"
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА в байтах.  
  
## Синтаксис  
  
```  
  
      void SetBlobSizeLimit(  
   DBLENGTH nBlobSize   
);  
```  
  
#### Параметры  
 `nBlobSize`  
 Указывает предел размера БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА.  
  
## Заметки  
 Задает максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА в байтах. данные столбца большая, чем это значение рассматривается как БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ.  Некоторые поставщики позволяют очень большие размеры для столбцов \(например, 2 ГБ\).  Вместо попытка для распределения памяти для столбца этот размер, обычно пытаются привязать эти столбцы в виде больших двоичных объектов.  В этом способом не следует выделить всю память, но все равно можно прочитать все данные, не усечения.  Однако некоторые случаи, в которых может потребоваться выполнить `CDynamicAccessor` для привязки большие столбцы в собственных типах данных.  Для этого необходимо вызвать метод `SetBlobSizeLimit` до вызова функции **Открыть**.  
  
 Метод [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) в конструкторе задает максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА значение по умолчанию 8,000 байт.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)