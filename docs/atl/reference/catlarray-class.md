---
title: "CAtlArray Class | Microsoft Docs"
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
  - "ATL::CAtlArray"
  - "ATL.CAtlArray"
  - "CAtlArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlArray class"
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует объект массива.  
  
## Синтаксис  
  
```  
  
      template<   
   typename E,  
   class ETraits = CElementTraits< E >   
>  
class CAtlArray  
```  
  
#### Параметры  
 *E*  
 Тип данных, хранимых в массиве.  
  
 *ETraits*  
 Код, используемый для копирования или перемещения элементов.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Add](../Topic/CAtlArray::Add.md)|Вызовите этот метод, чтобы добавить элемент к объекту массива.|  
|[Добавление](../Topic/CAtlArray::Append.md)|Вызывайте этот метод для добавления содержимого одного массива в конец другого.|  
|[AssertValid](../Topic/CAtlArray::AssertValid.md)|Вызовите этот метод, чтобы подтвердить, что объект массива является допустимым.|  
|[CAtlArray](../Topic/CAtlArray::CAtlArray.md)|Конструктор.|  
|[~CAtlArray](../Topic/CAtlArray::~CAtlArray.md)|Деструктор.|  
|[Копировать](../Topic/CAtlArray::Copy.md)|Вызывайте этот метод для копирования элементов одного массива в другой.|  
|[FreeExtra](../Topic/CAtlArray::FreeExtra.md)|Вызовите этот метод, чтобы удалить все пустые элементы из массива.|  
|[GetAt](../Topic/CAtlArray::GetAt.md)|Вызовите этот метод, чтобы получить один элемент из объекта массива.|  
|[GetCount](../Topic/CAtlArray::GetCount.md)|Вызовите этот метод, чтобы возвратить количество элементов, хранящихся в массиве.|  
|[GetData](../Topic/CAtlArray::GetData.md)|Вызовите этот метод, чтобы вернуть указатель на первый элемент в массиве.|  
|[InsertArrayAt](../Topic/CAtlArray::InsertArrayAt.md)|Этот метод вызывается для вставки одного массива в другой.|  
|[InsertAt](../Topic/CAtlArray::InsertAt.md)|Этот метод вызывается для вставки нового элемента \(или несколько копий элемента\) на объект массива.|  
|[IsEmpty](../Topic/CAtlArray::IsEmpty.md)|Вызывайте этот метод для проверки, если массив пуст.|  
|[Атрибут RemoveAll](../Topic/CAtlArray::RemoveAll.md)|Вызовите этот метод, чтобы удалить все элементы из объекта массива.|  
|[RemoveAt](../Topic/CAtlArray::RemoveAt.md)|Вызовите этот метод, чтобы удалить один или несколько элементов из массива.|  
|[SetAt](../Topic/CAtlArray::SetAt.md)|Вызовите этот метод, чтобы задать значение элемента в объекте массива.|  
|[SetAtGrow](../Topic/CAtlArray::SetAtGrow.md)|Вызовите этот метод, чтобы задать значение элемента в объекте массива развернуть массив.|  
|[SetCount](../Topic/CAtlArray::SetCount.md)|Вызовите этот метод, чтобы задать размер объекта массива.|  
  
### Операторы  
  
|||  
|-|-|  
|[оператор &#91;&#93;](../Topic/CAtlArray::operator.md)|Вызовите этот оператор, чтобы получить ссылку на элемент в массиве.|  
  
### Определения типов  
  
|||  
|-|-|  
|[INARGTYPE](../Topic/CAtlArray::INARGTYPE.md)|Тип данных, используемый для суммирующих элементов в массив.|  
|[OUTARGTYPE](../Topic/CAtlArray::OUTARGTYPE.md)|Тип данных, используемый для извлечения элементов из массива.|  
  
## Заметки  
 **CAtlArray** предоставляет методы для создания и управления массив элементов пользовательского типа.  Хотя аналогичного стандартным массивам c\#, объект **CAtlArray** может динамически сжатие и увеличиваться по мере необходимости.  Массива индекса всегда начинается в позиции 0, а верхняя граница могут быть устранены или разрешенный, чтобы развернуть как новые элементы добавлены.  
  
 Для массивов с небольшим количеством элементов, класс [CSimpleArray](../../atl/reference/csimplearray-class.md) библиотеки ATL можно использовать.  
  
 **CAtlArray** тесно связан с классом **CArray** MFC и будет работать в проекте MFC, albeit без поддержки сериализации.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Образец MMXSwarm](../../top/visual-cpp-samples.md)   
 [Образец DynamicConsumer](../../top/visual-cpp-samples.md)   
 [Образец UpdatePV](../../top/visual-cpp-samples.md)   
 [Образец бегущей строки](../../top/visual-cpp-samples.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)