---
title: "CByteArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CByteArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], байт"
  - "массивы байтов"
  - "CByteArray class"
  - "MFC collection classes, массивы байтов"
ms.assetid: 53d4a512-657c-4187-9609-e3f5339a78e0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CByteArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает динамические массивы байтов.  
  
## Синтаксис  
  
```  
class CByteArray : public CObject  
```  
  
## Члены  
 Функции\-члены `CByteArray` похожи на функции\-членам класса [CObArray](../../mfc/reference/cobarray-class.md).  Сходство вследствие этого, можно использовать документации `CObArray` для особенностях функции\-члена.  Везде, где можно увидеть указатель `CObject` в качестве параметра или возвращаемого значения функции, замените **байт**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 например, преобразуется в  
  
 `BYTE CByteArray::GetAt( int <nIndex> ) const;`  
  
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
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Возвращает ссылку на временную байту в массиве.|  
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
 `CByteArray` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Если массив байтов, хранящийся в архив или с перегруженным оператора insert \(**\<\<**\) или функцией\-членом `Serialize`, каждый элемент которого, в свою очередь, для сериализации.  
  
> [!NOTE]
>  Перед использованием массива, используйте `SetSize` чтобы установить его размер и выделить память для него.  Если не используется `SetSize`, то добавление элементов в массив часто вызывают быть reallocated и скопировать его.  Частое переразмещение и копирование неработоспособны и может разделить память.  
  
 Если требуется отладить выход из отдельных элементов в массиве необходимо установить глубину объекта `CDumpContext` значение 1 или больше.  
  
 Дополнительные сведения об использовании `CByteArray` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CByteArray`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)