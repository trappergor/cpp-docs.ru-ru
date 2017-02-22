---
title: "CObArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CObArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], Тип объекта"
  - "массивы [C++], указатели"
  - "CObArray class"
  - "массивы объектов, CObArray class"
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CObArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает массивы указателей `CObject`.  
  
## Синтаксис  
  
```  
class CObArray : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Создает пустой массив для указателей `CObject`.|  
  
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
 Эти массивы объектов похожи на массивы c\#, однако они могут динамически сжатие и увеличиваться по мере необходимости.  
  
 Индекс массива, начиная всегда в позиции 0.  Можно выбрать, следует ли разрешить исправить границы или массив, чтобы развернуть при добавлении элементов за границами текущего.  Память выделена сопредельн на границе, даже если некоторые элементы равны null.  
  
 В Win32, размер объекта `CObArray` ограничивается только доступной памятью.  
  
 Как и в случае с массивом c время выборки для элемента индексированного `CObArray` постоянным и не зависит от размера массива.  
  
 `CObArray` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Если массив указателей `CObject` хранится в архив или с перегруженным оператора insert или функцией\-членом `Serialize`, то каждый элемент `CObject`, в свою очередь, сериализован вместе с своим индексом массива.  
  
 Если требуется дамп отдельных элементов `CObject` в массиве, необходимо установить глубину объекта `CDumpContext` значение 1 или больше.  
  
 Если объект `CObArray` удаления или при его элементы удалены только указатели `CObject`, а не объекты удалены они ссылаются.  
  
> [!NOTE]
>  Перед использованием массива, используйте `SetSize` чтобы установить его размер и выделить память для него.  Если не используется `SetSize`, то добавление элементов в массив часто вызывают быть reallocated и скопировать его.  Частое переразмещение и копирование неработоспособны и может разделить память.  
  
 Источник класса массива похож на вывод списка.  Дополнительные сведения о выводе одноцелевого класса списка см. в статье [коллекции](../../mfc/collections.md).  
  
> [!NOTE]
>  Необходимо использовать макрос `IMPLEMENT_SERIAL` в реализации производного класса, если планируется сериализация массива.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CObArray`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CStringArray Class](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CByteArray Class](../../mfc/reference/cbytearray-class.md)   
 [CWordArray Class](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray Class](../Topic/CDWordArray%20Class.md)