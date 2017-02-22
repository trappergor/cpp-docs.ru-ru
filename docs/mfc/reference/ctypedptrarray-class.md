---
title: "CTypedPtrArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrArray class"
  - "pointer arrays"
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CTypedPtrArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет типобезопасную "программу\-оболочку" для объектов класса `CPtrArray` или `CObArray`.  
  
## Синтаксис  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### Параметры  
 `BASE_CLASS`  
 Базовый класс типизированного класса массива указателей; должен иметь класс массива \(`CObArray` или `CPtrArray`\).  
  
 `TYPE`  
 Тип элементов, хранящихся в массиве базового класса.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTypedPtrArray::Add](../Topic/CTypedPtrArray::Add.md)|Добавляет новый элемент в конец массива.  Растет массив, если обязательный|  
|[CTypedPtrArray::Append](../Topic/CTypedPtrArray::Append.md)|Добавляет содержимое одного массива в конец другого.  Растет массив, если обязательный|  
|[CTypedPtrArray::Copy](../Topic/CTypedPtrArray::Copy.md)|Копирует другой массив в массив. растет массив, если требуемый.|  
|[CTypedPtrArray::ElementAt](../Topic/CTypedPtrArray::ElementAt.md)|Возвращает временной ссылку на указатель элемента в массиве.|  
|[CTypedPtrArray::GetAt](../Topic/CTypedPtrArray::GetAt.md)|Возвращает значение по заданному индексу.|  
|[CTypedPtrArray::InsertAt](../Topic/CTypedPtrArray::InsertAt.md)|Вставляет элемент \(или все элементы в других массив\) по указанному индексу.|  
|[CTypedPtrArray::SetAt](../Topic/CTypedPtrArray::SetAt.md)|Задает значение для данного индекса; массив не разрешенный увеличиваться.|  
|[CTypedPtrArray::SetAtGrow](../Topic/CTypedPtrArray::SetAtGrow.md)|Задает значение для данного индекса; растет массив, если требуемый.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTypedPtrArray::operator](../Topic/CTypedPtrArray::operator.md)|Получает или задает элемент по указанному индексу.|  
  
## Заметки  
 При использовании `CTypedPtrArray`, а не `CPtrArray` или `CObArray`, средства проверки типа C\+\+ кроме ошибки, вызванные рассогласованными типами указателя.  
  
 Кроме того, программа\-оболочка `CTypedPtrArray` выполняет многие приведения, необходимой при использовании `CObArray` или `CPtrArray`.  
  
 Поскольку все функции `CTypedPtrArray` встроенным использование данного шаблона в значительной степени не влияет на размер или скорости кода.  
  
 Дополнительные сведения об использовании `CTypedPtrArray` см. в разделе статьи [коллекции](../../mfc/collections.md) и [Шаблон\- на основе классов](../Topic/Template-Based%20Classes.md).  
  
## Иерархия наследования  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## Требования  
 **Header:**  afxtempl.h  
  
## См. также  
 [Образец MFC СОБИРАЕТ](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)