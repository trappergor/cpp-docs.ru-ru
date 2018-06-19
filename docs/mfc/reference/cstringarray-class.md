---
title: Класс CStringArray | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringArray
- AFXCOLL/CStringArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3ebc30304f2d194a10b71f832b42039bac6a53
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375510"
---
# <a name="cstringarray-class"></a>Класс CStringArray
Поддерживает массивы [CString](../../atl-mfc-shared/using-cstring.md) объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStringArray : public CObject  
```  
  
## <a name="members"></a>Участники  
 Функции-члены `CStringArray` похожи на функции-члены класса [CObArray](../../mfc/reference/cobarray-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObArray`. Если вы видите `CObject` указатель как возвращаемое значение, замените [CString](../../atl-mfc-shared/using-cstring.md) объекта (не [CString](../../atl-mfc-shared/using-cstring.md) указатель). Если вы видите указатель `CObject` как параметр функции, замените `LPCTSTR`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 , например, преобразуется в  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 и  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 преобразуется в  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Создает пустой массив.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Возвращает значение по указанному индексу.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Возвращает количество элементов в массиве.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Разрешает доступ к элементам в массиве. Может быть **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Возвращает количество элементов в массиве.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Возвращает самый большой допустимый индекс.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Определяет, пуст ли массив.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Удаляет все элементы из этого массива.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Удаляет элемент по указанному индексу.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Задает число элементов, которые будут храниться в этом массиве.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 `CStringArray` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Если массив объект `CString` сохраняется в архив с помощью перегруженного оператора вставки или функции-члена `Serialize`, каждый элемент сериализуется.  
  
> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных строковых элементов в массиве, задайте для глубины контекста дампа 1 или большее значение.  
  
 При удалении массива `CString` или его элементов, строковая память освобождается соответствующим образом.  
  
 Дополнительные сведения об использовании `CStringArray`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



