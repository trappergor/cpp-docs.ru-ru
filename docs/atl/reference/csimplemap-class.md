---
title: "CSimpleMap Class | Microsoft Docs"
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
  - "ATL::CSimpleMap"
  - "ATL.CSimpleMap"
  - "CSimpleMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMap class"
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс обеспечивает поддержку простых массивов сопоставления.  
  
## Синтаксис  
  
```  
  
      template <   
   class TKey,  
   class TVal,  
   class TEqual = CSimpleMapEqualHelper< TKey, TVal >   
>   
class CSimpleMap  
```  
  
#### Параметры  
 `TKey`  
 Тип ключевого положения.  
  
 `TVal`  
 Тип значения.  
  
 `TEqual`  
 Объект признака, указав тест равенства элементов типа `T`.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleMap::\_ArrayElementType](../Topic/CSimpleMap::_ArrayElementType.md)|Typedef для типа значения.|  
|[CSimpleMap::\_ArrayKeyType](../Topic/CSimpleMap::_ArrayKeyType.md)|Typedef для ключевого типа.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleMap::CSimpleMap](../Topic/CSimpleMap::CSimpleMap.md)|Конструктор.|  
|[CSimpleMap::~CSimpleMap](../Topic/CSimpleMap::~CSimpleMap.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleMap::Add](../Topic/CSimpleMap::Add.md)|Добавляет ключ и связанное с ним значение в массив сопоставления.|  
|[CSimpleMap::FindKey](../Topic/CSimpleMap::FindKey.md)|Находит указанный ключ.|  
|[CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)|Находит указанное значение.|  
|[CSimpleMap::GetKeyAt](../Topic/CSimpleMap::GetKeyAt.md)|Извлекает указанный ключ.|  
|[CSimpleMap::GetSize](../Topic/CSimpleMap::GetSize.md)|Возвращает количество записей в массиве сопоставления.|  
|[CSimpleMap::GetValueAt](../Topic/CSimpleMap::GetValueAt.md)|Извлекает указанное значение.|  
|[CSimpleMap::Lookup](../Topic/CSimpleMap::Lookup.md)|Возвращает значение, связанное с указанным ключом.|  
|[CSimpleMap::Remove](../Topic/CSimpleMap::Remove.md)|Удаляет ключ и соответствующее значение.|  
|[CSimpleMap::RemoveAll](../Topic/CSimpleMap::RemoveAll.md)|Удаляет все ключи и значения.|  
|[CSimpleMap::RemoveAt](../Topic/CSimpleMap::RemoveAt.md)|Удаляет указанный ключ и соответствующее значение.|  
|[CSimpleMap::ReverseLookup](../Topic/CSimpleMap::ReverseLookup.md)|Возвращает ключ, связанный с заданным значением.|  
|[CSimpleMap::SetAt](../Topic/CSimpleMap::SetAt.md)|Устанавливает значение, связанный с указанным ключом.|  
|[CSimpleMap::SetAtIndex](../Topic/CSimpleMap::SetAtIndex.md)|Устанавливает указанные ключ и значение.|  
  
## Заметки  
 `CSimpleMap` обеспечивает поддержку простых массивов сопоставления любого заданного типа, `T` для управления неупорядоченными массив ключевых положений и связанных с ними значений.  
  
 Параметр `TEqual` предоставляет середины определение функцию равенства, 2 элементов типа `T`.  Путем создания класса, аналогичный [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), можно изменить поведение теста равенства для любого заданного массива.  Например, при работе с массивом указателей, может быть полезно для определения равенства как в зависимости от значений указателей ссылаются.  Реализация по умолчанию использует **operator\=\=\(\)**.  
  
 И `CSimpleMap` и [CSimpleArray](../../atl/reference/csimplearray-class.md) предоставляются для совместимости с предыдущими версиями библиотеки ATL и более полные и более эффективные реализации коллекции предоставляются [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap](../../atl/reference/catlmap-class.md).  
  
 В отличие от других коллекций сопоставления в библиотеке ATL и MFC этот класс реализуется с простым массивом, требуют линейного поиска и уточняющего поиска.  `CAtlMap` должно использоваться, если массив содержит большое число элементов.  
  
## Требования  
 **Header:** atlsimpcoll.h  
  
## Пример  
 [!CODE [NVC_ATL_Utilities#91](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#91)]  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)