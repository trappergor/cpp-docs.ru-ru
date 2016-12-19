---
title: "CUIntArray Class | Microsoft Docs"
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
  - "CUIntArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], индексированные"
  - "CUIntArray class"
  - "indexed arrays"
  - "INT"
  - "UINT"
  - "WORD data type"
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUIntArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает массивы целых чисел без знака.  
  
## Синтаксис  
  
```  
class CUIntArray : public CObject  
```  
  
## Члены  
 Функции\-члены `CUIntArray` похожи на функции\-членам класса [CObArray](../../mfc/reference/cobarray-class.md).  Сходство вследствие этого, можно использовать документации `CObArray` для особенностях функции\-члена.  Везде, где можно увидеть указатель `CObject` в качестве параметра или возвращаемого значения функции, замените **UINT**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 например, преобразуется в  
  
 `UINT CUIntArray::GetAt( int <nIndex> ) const;`  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Создает пустой массив.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Добавляет элемент в конец массива; растет массив, если требуемый.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Добавляет другой массив в массив. растет массив, если требуемый.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Копирует другой массив в массив. растет массив, если требуемый.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Возвращает временной ссылку на указатель элемента в массиве.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Высвобождает всю неиспользуемую память над текущим границей.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Возвращает значение по заданному индексу.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Получает число элементов в данном массиве.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Разрешает доступ к элементам массива.  Может быть **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Получает число элементов в данном массиве.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Возвращает максимальный допустимый индекс.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Вставляет элемент \(или все элементы в других массив\) по указанному индексу.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Определяет, если массив пуст.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Удаляет все элементы из этого массива.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Удаляет элемент по указанному индексу.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Задает значение для данного индекса; массив не разрешенный увеличиваться.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Задает значение для данного индекса; растет массив, если требуемый.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Задает количество элементов, которое должно содержаться в этом массиве.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Получает или задает элемент по указанному индексу.|  
  
## Заметки  
 Целое число без знака или **UINT**, отличные от слов и doublewords, в котором физический размер **UINT** может меняться в зависимости от операционной среды целевого объекта.  **UINT** Тот же размер, как doubleword.  
  
 `CUIntArray` содержит макрос [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) для поддержки доступа типа во время выполнения и сбрасывать на [CDumpContext](../../mfc/reference/cdumpcontext-class.md) объект.  Если требуется дамп отдельных элементов в виде целого числа без знака, то необходимо задать глубину контекста дампа значение 1 или больше.  Массивы целого числа без знака не может быть сериализован.  
  
> [!NOTE]
>  Перед использованием массива, используйте `SetSize` чтобы установить его размер и выделить память для него.  Если не используется `SetSize`, то добавление элементов в массив часто вызывают быть reallocated и скопировать его.  Частое переразмещение и копирование неработоспособны и может разделить память.  
  
 Дополнительные сведения об использовании `CUIntArray` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CUIntArray`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)