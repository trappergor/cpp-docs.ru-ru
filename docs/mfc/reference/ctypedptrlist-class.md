---
title: "CTypedPtrList-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList class
- type-safe collections
- lists [C++]
- template classes, CTypedPtrList class
- linked lists [C++]
- pointer lists
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ca8d868333aa977710e387fc1bb13271dc8f99fa
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrlist-class"></a>CTypedPtrList-класс
Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrList`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовый класс для класса list типизированный указатель; должен быть классом список указатель ( `CObList` или `CPtrList`).  
  
 `TYPE`  
 Тип элементов, хранящихся в списке базовых классов.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) в начало списка (делает нового заголовка).|  
|[CTypedPtrList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) конца списка (делает новый заключительного фрагмента).|  
|[CTypedPtrList::GetAt](#getat)|Возвращает элемент в заданной позиции.|  
|[CTypedPtrList::GetHead](#gethead)|Возвращает элемент заголовка списка (не может быть пустым).|  
|[CTypedPtrList::GetNext](#getnext)|Получает следующий элемент для итерации.|  
|[CTypedPtrList::GetPrev](#getprev)|Возвращает предыдущий элемент для итерации.|  
|[CTypedPtrList::GetTail](#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CTypedPtrList::RemoveHead](#removehead)|Удаляет элемент в начало списка.|  
|[CTypedPtrList::RemoveTail](#removetail)|Удаляет элемент из конца списка.|  
|[CTypedPtrList::SetAt](#setat)|Задает элемент в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrList` вместо `CObList` или `CPtrList`, средство проверки типов C++ позволяет избежать ошибок, вызванных указатель несовпадающие типы.  
  
 Кроме того `CTypedPtrList` оболочка выполняет большую часть приведения, которое было бы необходимо при использовании `CObList` или `CPtrList`.  
  
 Так как все `CTypedPtrList` функций, встроенных, этот шаблон не влияет на значительно размер или скорость кода.  
  
 Списки производным от `CObList` может быть сериализован, но которые являются производными от `CPtrList` невозможно.  
  
 Когда `CTypedPtrList` удалить объект, или при удалении элементов, удаляются только указатели, не сущностями, которые они ссылаются.  
  
 Дополнительные сведения об использовании `CTypedPtrList`, см. в статьях [коллекции](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="example"></a>Пример  
 В этом примере создается экземпляр `CTypedPtrList`, добавляет один объект, сериализует список на диск и затем удаляет объект:  
  
 [!code-cpp[NVC_MFCCollections&#110;](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&#111;](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="addhead"></a>CTypedPtrList::AddHead  
 Эта функция-член вызывает `BASE_CLASS` **:: AddHead**.  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Тип элементов, хранящихся в списке базовых классов.  
  
 `newElement`  
 Указатель на объект для добавления в этот список. Объект **NULL** допустимое значение.  
  
 `BASE_CLASS`  
 Базовый класс для класса list типизированный указатель; должен быть классом список указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в `pNewList` будут добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Первая версия добавляет новый элемент перед начало списка. Вторая версия добавляет другой список элементов, прежде чем заголовок.  
  
##  <a name="addtail"></a>CTypedPtrList::AddTail  
 Эта функция-член вызывает `BASE_CLASS` **:: AddTail**.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Тип элементов, хранящихся в списке базовых классов.  
  
 `newElement`  
 Указатель на объект для добавления в этот список. Объект **NULL** допустимое значение.  
  
 `BASE_CLASS`  
 Базовый класс для класса list типизированный указатель; должен быть классом список указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в `pNewList` будут добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Первая версия добавляет новый элемент после конца списка. Вторая версия добавляет другой список элементов после конца списка.  
  
##  <a name="getat"></a>CTypedPtrList::GetAt  
 Переменная типа **ПОЗИЦИИ** является ключом для списка.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в списке.  
  
 *положение*  
 Объект **ПОЗИЦИИ** значение, возвращенное предыдущим `GetHeadPosition` или **найти** вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CTypedPtrList**, затем `GetAt` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CTypedPtrList`, затем `GetAt` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Не соответствует индекс, и не может работать с **ПОЗИЦИИ** значение самостоятельно. `GetAt`Извлекает `CObject` указатель, связанный с заданной позиции.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>CTypedPtrList::GetHead  
 Получает указатель, представляющий элемент заголовка этого списка.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CTypedPtrList**, затем `GetHead` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CTypedPtrList`, затем `GetHead` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `GetHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="getnext"></a>CTypedPtrList::GetNext  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение следующей записи в списке.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, содержащихся в данном списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другие вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CTypedPtrList**, затем `GetNext` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CTypedPtrList`, затем `GetNext` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNext` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetHeadPosition` или [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Если полученный элемент является последним в списке, то новое значение `rPosition` равен **NULL**.  
  
 Можно удалить элемент во время итерации. В примере показано [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>CTypedPtrList::GetPrev  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение предыдущей записи в списке.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, содержащихся в данном списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetPrev` или других вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CTypedPtrList**, затем `GetPrev` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CTypedPtrList`, затем `GetPrev` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetPrev` в обратной итерации цикла, если установить начальное положение, с помощью вызова `GetTailPosition` или **найти**.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Если полученный элемент является первым в списке, затем новое значение `rPosition` равен **NULL**.  
  
##  <a name="gettail"></a>CTypedPtrList::GetTail  
 Получает указатель, представляющий элемент заголовка этого списка.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CTypedPtrList**, затем `GetTail` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CTypedPtrList`, затем `GetTail` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `GetTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="removehead"></a>CTypedPtrList::RemoveHead  
 Удаляет элемент в начало списка и возвращает его.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель ранее в начало списка. Этот указатель имеет тип, заданный параметром шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `RemoveHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="removetail"></a>CTypedPtrList::RemoveTail  
 Удаляет элемент из конца списка и возвращает его.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указав тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель ранее в конце списка. Этот указатель имеет тип, заданный параметром шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `RemoveTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="setat"></a>CTypedPtrList::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 **ПОЗИЦИИ** элемента, чтобы задать.  
  
 *ТИП*  
 Тип элементов, хранящихся в списке базовых классов.  
  
 `newElement`  
 Указатель на объект для записи в списке.  
  
### <a name="remarks"></a>Примечания  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Не соответствует индекс, и не может работать с **ПОЗИЦИИ** значение самостоятельно. `SetAt`Записывает указателя на объект в указанной позиции в списке.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Дополнительные примечания см. в разделе [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPtrList](../../mfc/reference/cptrlist-class.md)   
 [Класс cObList](../../mfc/reference/coblist-class.md)

