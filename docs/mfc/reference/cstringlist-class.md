---
title: "Класс CStringList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringList
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], lists
- lists, string
- CStringList class
- strings [C++], collections
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b67104e330890ffe8f67bac0dd3b129c7742a29
ms.lasthandoff: 02/24/2017

---
# <a name="cstringlist-class"></a>Класс CStringList
Поддерживает списки объектов `CString` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>Члены  
 Функции-члены `CStringList` похожи на функции-члены класса [CObList](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Если вы видите `CObject` указатель как возвращаемое значение, замените `CString` (не `CString` указатель). Если вы видите `CObject` указатель как параметр функции, замените `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 , например, преобразуется в  
  
 `CString& CStringList::GetHead() const;`  
  
 и  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 преобразуется в  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Создает пустой список.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Добавляет элемент (или все элементы в другом списке) в начало списка (делает нового заголовка).|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Добавляет элемент (или все элементы в другом списке) конца списка (делает новый заключительного фрагмента).|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Возвращает положение элемента, заданного значением указателя.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Возвращает позицию указанного отсчитываемый от нуля индекс элемента.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Возвращает элемент в заданной позиции.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Возвращает количество элементов в этом списке.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Возвращает элемент заголовка списка (не может быть пустым).|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Возвращает позицию головной элемент списка.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Получает следующий элемент для итерации.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Возвращает предыдущий элемент для итерации.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Возвращает количество элементов в этом списке.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Возвращает позицию заключительного элемента списка.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Вставляет новый элемент после заданной позиции.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Вставляет новый элемент до заданной позиции.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Проверяет условие пустой список (нет элементов).|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Удаляет все элементы из списка.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Удаляет элемент из списка, в заданном порядке.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Удаляет элемент в начало списка.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Удаляет элемент из конца списка.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Задает элемент в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 Все сравнения выполняются по значению, это означает, что вместо адреса строк сравниваются символы в строке.  
  
 `CStringList` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Если список `CString` объекты хранятся в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, каждый из которых `CString` элемент сериализуется в свою очередь.  
  
 Если вам требуется дамп отдельных `CString` элементов, необходимо задать глубины контекста дампа 1 или больше.  
  
 Дополнительные сведения об использовании `CStringList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




