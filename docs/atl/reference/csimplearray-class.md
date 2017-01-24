---
title: "CSimpleArray Class | Microsoft Docs"
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
  - "ATL.CSimpleArray"
  - "ATL::CSimpleArray"
  - "CSimpleArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArray class"
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для управления простой массив.  
  
## Синтаксис  
  
```  
  
      template <  
   class T,  
   class TEqual = CSimpleArrayEqualHelper< T >  
>   
class CSimpleArray  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в массиве.  
  
 `TEqual`  
 Объект признака, указав тест равенства элементов типа `T`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleArray::CSimpleArray](../Topic/CSimpleArray::CSimpleArray.md)|Конструктор для простого массива.|  
|[CSimpleArray::~CSimpleArray](../Topic/CSimpleArray::~CSimpleArray.md)|Деструктор для простого массива.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleArray::Add](../Topic/CSimpleArray::Add.md)|Добавляет новый элемент в массив.|  
|[CSimpleArray::Find](../Topic/CSimpleArray::Find.md)|Находит элемент в массиве.|  
|[CSimpleArray::GetData](../Topic/CSimpleArray::GetData.md)|Возвращает указатель на данные, хранящиеся в массиве.|  
|[CSimpleArray::GetSize](../Topic/CSimpleArray::GetSize.md)|Возвращает количество элементов, хранящихся в массиве.|  
|[CSimpleArray::Remove](../Topic/CSimpleArray::Remove.md)|Удаляет заданный элемент из массива.|  
|[CSimpleArray::RemoveAll](../Topic/CSimpleArray::RemoveAll.md)|Удаляет все элементы из массива.|  
|[CSimpleArray::RemoveAt](../Topic/CSimpleArray::RemoveAt.md)|Удаляет указанный элемент из массива.|  
|[CSimpleArray::SetAtIndex](../Topic/CSimpleArray::SetAtIndex.md)|Устанавливает указанный элемент в массиве.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleArray::operator](../Topic/CSimpleArray::operator.md)|Извлекает элемент из массива.|  
|[CSimpleArray::operator \=](../Topic/CSimpleArray::operator%20=.md)|Оператор присваивания.|  
  
## Заметки  
 `CSimpleArray` предоставляет методы для создания и управления простой массив любого заданного типа `T`.  
  
 Параметр `TEqual` предоставляет середины определение функцию равенства, 2 элементов типа `T`.  Путем создания класса, аналогичный [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), можно изменить поведение теста равенства для любого заданного массива.  Например, при работе с массивом указателей, может быть полезно для определения равенства как в зависимости от значений указателей ссылаются.  Реализация по умолчанию использует **operator\=\(\)**.  
  
 И `CSimpleArray` и [CSimpleMap](../../atl/reference/csimplemap-class.md) предназначены для нескольких элементов.  [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap](../../atl/reference/catlmap-class.md) должны использоваться, если массив содержит большое число элементов.  
  
## Требования  
 **Header:** atlsimpcoll.h  
  
## Пример  
 [!CODE [NVC_ATL_Utilities#86](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#86)]  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)