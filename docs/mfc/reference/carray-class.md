---
title: "CArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], classes"
  - "CArray class"
  - "классы коллекций, template-based"
  - "шаблоны, классы коллекций"
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает массивы, как массивы c\#, но может динамически уменьшить и увеличиваться по мере необходимости.  
  
## Синтаксис  
  
```  
template < class TYPE, class ARG_TYPE = const TYPE& >   
class CArray :   
   public CObject  
```  
  
#### Параметры  
 `TYPE`  
 Параметр шаблона, указывающее тип объектов, содержащихся в массиве.  `TYPE` параметр, который возвращается `CArray`.  
  
 `ARG` *\_* `TYPE`  
 Параметр шаблона, указывающее тип аргумента, который используется для доступа к объектам, хранящиеся в массиве.  Часто ссылка на `TYPE`.  `ARG_TYPE` параметр, который передается `CArray`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArray::CArray](../Topic/CArray::CArray.md)|Создает пустой массив.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArray::Add](../Topic/CArray::Add.md)|Добавляет элемент в конец массива; растет массив, если требуемый.|  
|[CArray::Append](../Topic/CArray::Append.md)|Добавляет другой массив в массив. растет массив, если обязательный|  
|[CArray::Copy](../Topic/CArray::Copy.md)|Копирует другой массив в массив. растет массив, если требуемый.|  
|[CArray::ElementAt](../Topic/CArray::ElementAt.md)|Возвращает временной ссылку на указатель элемента в массиве.|  
|[CArray::FreeExtra](../Topic/CArray::FreeExtra.md)|Высвобождает всю неиспользуемую память над текущим границей.|  
|[CArray::GetAt](../Topic/CArray::GetAt.md)|Возвращает значение по заданному индексу.|  
|[CArray::GetCount](../Topic/CArray::GetCount.md)|Получает число элементов в данном массиве.|  
|[CArray::GetData](../Topic/CArray::GetData.md)|Разрешает доступ к элементам массива.  Может быть **NULL**.|  
|[CArray::GetSize](../Topic/CArray::GetSize.md)|Получает число элементов в данном массиве.|  
|[CArray::GetUpperBound](../Topic/CArray::GetUpperBound.md)|Возвращает максимальный допустимый индекс.|  
|[CArray::InsertAt](../Topic/CArray::InsertAt.md)|Вставляет элемент \(или все элементы в других массив\) по указанному индексу.|  
|[CArray::IsEmpty](../Topic/CArray::IsEmpty.md)|Определяет, является ли массив пуст.|  
|[CArray::RemoveAll](../Topic/CArray::RemoveAll.md)|Удаляет все элементы из этого массива.|  
|[CArray::RemoveAt](../Topic/CArray::RemoveAt.md)|Удаляет элемент по указанному индексу.|  
|[CArray::SetAt](../Topic/CArray::SetAt.md)|Задает значение для данного индекса; массив не разрешенный увеличиваться.|  
|[CArray::SetAtGrow](../Topic/CArray::SetAtGrow.md)|Задает значение для данного индекса; растет массив, если требуемый.|  
|[CArray::SetSize](../Topic/CArray::SetSize.md)|Задает количество элементов, которое должно содержаться в этом массиве.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArray::operator](../Topic/CArray::operator.md)|Получает или задает элемент по указанному индексу.|  
  
## Заметки  
 Индекс массива, начиная всегда в позиции 0.  Можно выбрать, следует ли разрешить исправить границы или массив, чтобы развернуть при добавлении элементов за границами текущего.  Память выделена сопредельн на границе, даже если некоторые элементы равны null.  
  
> [!NOTE]
>  Большинство методов, которые изменяют размер объекта `CArray` или добавляют элементы к нему использование [memcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) к элементам перемещения.  Это проблемы, так как `memcpy_s` не совместим с любыми объектами, которые требуют вызова конструктора.  Если элементы в `CArray` не совместимы с `memcpy_s`, необходимо создать новое `CArray` нужного размера.  После этого следует использовать [CArray::Copy](../Topic/CArray::Copy.md) и [CArray::SetAt](../Topic/CArray::SetAt.md) для заполнения новый массив, так как эти методы используют оператор присваивания вместо `memcpy_s`.  
  
 Как и в случае с массивом c время выборки для элемента индексированного `CArray` постоянным и не зависит от размера массива.  
  
> [!TIP]
>  Перед использованием массива, используйте [SetSize](../Topic/CArray::SetSize.md) чтобы установить его размер и выделить память для него.  Если не используется `SetSize`, то добавление элементов в массив часто вызывают быть reallocated и скопировать его.  Частое переразмещение и копирование неработоспособны и может разделить память.  
  
 Если требуется дамп отдельных элементов в массиве необходимо установить глубину объекта [CDumpContext](../../mfc/reference/cdumpcontext-class.md) значение 1 или больше.  
  
 Некоторые функции\-члены этого класса вызывают глобальные вспомогательные функции, необходимые для настройки для большинства польз класса `CArray`.  См. раздел [Вспомогательные объекты класса коллекции](../../mfc/reference/collection-class-helpers.md) в разделе "Макросы MFC и глобальные переменные".  
  
 Источник класса массива как вывод списка.  
  
 Дополнительные сведения об использовании `CArray` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CArray`  
  
## Требования  
 `Header:` afxtempl.h  
  
## См. также  
 [Образец MFC СОБИРАЕТ](../../top/visual-cpp-samples.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)   
 [Вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md)