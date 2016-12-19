---
title: "CStringData Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringData class"
  - "shared classes, CStringData"
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringData Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет данные строкового объекта.  
  
## Синтаксис  
  
```  
  
struct CStringData  
  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[AddRef](../Topic/CStringData::AddRef.md)|Увеличивает число ссылок объекта данных string.|  
|[data](../Topic/CStringData::data.md)|Возвращает символьные данные строкового объекта.|  
|[IsLocked](../Topic/CStringData::IsLocked.md)|Определяет, если буфер связанного объекта строки блокирована.|  
|[IsShared](../Topic/CStringData::IsShared.md)|Определяет, если буфер связанного объекта строки в настоящее время использовать совместно.|  
|[Блокировка](../Topic/CStringData::Lock.md)|Блокирует буфер связанного объекта строки.|  
|[Release](../Topic/CStringData::Release.md)|Освобождает строчный объект.|  
|[Unlock](../Topic/CStringData::Unlock.md)|Разблокирует буфер связанного объекта строки.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[nAllocLength](../Topic/CStringData::nAllocLength.md)|Длина выбранных данных в `XCHAR` s \(не включая завершения null\)|  
|[nDataLength](../Topic/CStringData::nDataLength.md)|Длина в настоящий момент, используемых данных в `XCHAR` s \(не включая завершения null\)|  
|[nRefs](../Topic/CStringData::nRefs.md)|Текущий счетчик ссылок объекта.|  
|[pStringMgr](../Topic/CStringData::pStringMgr.md)|Указатель на него строки данного объекта строки.|  
  
## Заметки  
 Этот класс должен использоваться только разработчиками, реализующий пользовательские диспетчеры строки.  Дополнительные сведения о пользовательских диспетчерах строки см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Этот класс инкапсулирует различные типы сведения и сведения, связанные с более высоким строковые объекты, например объекты [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md) или [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  Каждый более высокое строковый объект содержит указатель на объект, связанный `CStringData` несколько строковых объектов к точке на один и тот же объект данных string.  Эта связь представляется значения счетчика ссылок \(`nRefs`\) объекта `CStringData`.  
  
> [!NOTE]
>  В некоторых случаях строкового типа \(например, **CFixedString**\) не использует объект данных строки с более чем одним более высоким строковый объект.  Дополнительные сведения см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Эти данные структурируются.  
  
-   Диспетчер памяти \(типа [IAtlStringMgr](../Topic/IAtlStringMgr%20Class.md)\) строк.  
  
-   Текущая длина \([nDataLength](../Topic/CStringData::nDataLength.md)\) строк.  
  
-   Выбранная длина \([nAllocLength](../Topic/CStringData::nAllocLength.md)\) строк.  Для повышения производительности это может отличаться от текущей длиной строки  
  
-   Текущий счетчик ссылок \([nRefs](../Topic/CStringData::nRefs.md)\) объекта `CStringData`.  Это значение используется для определения того, строковые объекты используют один и тот же объект `CStringData`.  
  
-   Фактический буфер знаков \([данные](../Topic/CStringData::data.md)\) строк.  
  
    > [!NOTE]
    >  Фактический буфер символов строкового объекта выбрать диспетчером строки и добавить к объекту `CStringData`.  
  
## Требования  
 **Header:** atlsimpstr.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)