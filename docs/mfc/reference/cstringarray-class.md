---
title: "CStringArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], строки"
  - "CStringArray class"
  - "string arrays"
  - "строки [C++], коллекции"
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CStringArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает массивы объектов [CString](../../atl-mfc-shared/using-cstring.md).  
  
## Синтаксис  
  
```  
class CStringArray : public CObject  
```  
  
## Члены  
 Функции\-члены `CStringArray` аналогичны функциям\-членам класса [CObArray](../../mfc/reference/cobarray-class.md).  Из\-за этой схожести для изучения этой функции\-члена можно использовать справочную документацию по классу `CObArray`.  Если вы видите, что указатель `CObject` используется как возвращаемое значение, замените объект [CString](../../atl-mfc-shared/using-cstring.md) \(а не указатель [CString](../../atl-mfc-shared/using-cstring.md)\).  Если вы видите указатель `CObject` как параметр функции, замените `LPCTSTR`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 , например, преобразуется в  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 и  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 преобразуется в  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Создает пустой массив.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Возвращает значение по указанному индексу.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Возвращает количество элементов в массиве.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Разрешает доступ к элементам в массиве.  Допускается значение **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Возвращает количество элементов в массиве.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Возвращает самый большой допустимый индекс.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Вставляет элемент \(или все элементы в другом массиве\) по указанному индексу.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Определяет, пуст ли массив.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Удаляет все элементы из этого массива.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Удаляет элемент по указанному индексу.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Задает число элементов, которые будут храниться в этом массиве.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Получает или задает элемент с указанным индексом.|  
  
## Заметки  
 `CStringArray` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп.  Если массив объект `CString` сохраняется в архив с помощью перегруженного оператора вставки или функции\-члена `Serialize`, каждый элемент сериализуется.  
  
> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память.  Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память.  Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных строковых элементов в массиве, задайте для глубины контекста дампа 1 или большее значение.  
  
 При удалении массива `CString` или его элементов, строковая память освобождается соответствующим образом.  
  
 Дополнительные сведения об использовании `CStringArray` см. в статье [Коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CStringArray`  
  
## Требования  
 **Заголовок:** afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)