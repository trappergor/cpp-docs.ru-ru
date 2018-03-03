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
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 318373755ff05667d94b051dabf42822b34894b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Базовый класс для класса типизированных указателей списка; должен быть классом список указатель ( `CObList` или `CPtrList`).  
  
 `TYPE`  
 Тип элементов, хранящихся в списке базовых классов.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) в начало списка (делает нового заголовка).|  
|[CTypedPtrList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) заключительного списка (делает новый заключительного).|  
|[CTypedPtrList::GetAt](#getat)|Возвращает элемент в заданной позиции.|  
|[CTypedPtrList::GetHead](#gethead)|Возвращает элемент head списка (не может быть пустым).|  
|[CTypedPtrList::GetNext](#getnext)|Получает следующий элемент для выполнения итерации.|  
|[CTypedPtrList::GetPrev](#getprev)|Возвращает предыдущий элемент для выполнения итерации.|  
|[CTypedPtrList::GetTail](#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CTypedPtrList::RemoveHead](#removehead)|Удаляет элемент в начало списка.|  
|[CTypedPtrList::RemoveTail](#removetail)|Удаляет элемент с конца списка.|  
|[CTypedPtrList::SetAt](#setat)|Задает элемент в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrList` вместо `CObList` или `CPtrList`, средство проверки типов C++ позволяет избежать ошибок, вызванных типы несоответствие указателей.  
  
 Кроме того `CTypedPtrList` оболочки выполняет большую часть приведение, требуемый при использовании `CObList` или `CPtrList`.  
  
 Так как все `CTypedPtrList` функции — это встроенные, использование этого шаблона не влияет на значительно размер или скорость кода.  
  
 Списки производным от `CObList` может быть сериализован, но которые являются производными от `CPtrList` невозможно.  
  
 Когда `CTypedPtrList` объект удаляется или при его элементы будут удалены, удаляются только указатели, не сущностями, которые они ссылаются.  
  
 Дополнительные сведения об использовании `CTypedPtrList`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="example"></a>Пример  
 В этом примере создается экземпляр `CTypedPtrList`, добавляет один объект, сериализует списка на диск, а затем удаляет объект:  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
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
 Указатель на объект для добавления в этот список. Объект **NULL** является допустимым значением.  
  
 `BASE_CLASS`  
 Базовый класс для класса типизированных указателей списка; должен быть классом список указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в `pNewList` будет добавляться в этот список.  
  
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
 Указатель на объект для добавления в этот список. Объект **NULL** является допустимым значением.  
  
 `BASE_CLASS`  
 Базовый класс для класса типизированных указателей списка; должен быть классом список указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в `pNewList` будет добавляться в этот список.  
  
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
 Параметр шаблона, определяющий тип элементов, хранящихся в списке.  
  
 *положение*  
 Объект **ПОЗИЦИИ** значение, возвращенное предыдущим `GetHeadPosition` или **найти** вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CTypedPtrList**, затем `GetAt` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CTypedPtrList`, затем `GetAt` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. `GetAt`Извлекает `CObject` указатель, связанный с заданной позиции.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>CTypedPtrList::GetHead  
 Возвращает указатель, который представляет элемент head этого списка.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CTypedPtrList**, затем `GetHead` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CTypedPtrList`, затем `GetHead` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="getnext"></a>CTypedPtrList::GetNext  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение на следующую запись в списке.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, задающее тип элементов, содержащихся в этом списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CTypedPtrList**, затем `GetNext` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CTypedPtrList`, затем `GetNext` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNext` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetHeadPosition` или [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученный элемент является последним в списке, то новое значение `rPosition` равно **NULL**.  
  
 Существует возможность удалить элемент во время итерации. Далее приведен пример [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>CTypedPtrList::GetPrev  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение предыдущей записи в списке.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, задающее тип элементов, содержащихся в этом списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CTypedPtrList**, затем `GetPrev` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CTypedPtrList`, затем `GetPrev` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetPrev` в цикле перебора в обратном порядке, если установить начальное положение, с помощью вызова `GetTailPosition` или **найти**.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученного элемента является первым в списке, то новое значение `rPosition` равно **NULL**.  
  
##  <a name="gettail"></a>CTypedPtrList::GetTail  
 Возвращает указатель, который представляет элемент head этого списка.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CTypedPtrList**, затем `GetTail` возвращает указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CTypedPtrList`, затем `GetTail` возвращает ссылку на указатель типа, указанного в параметре шаблона *ТИПА*. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="removehead"></a>CTypedPtrList::RemoveHead  
 Удаляет элемент в начало списка и возвращает его.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель ранее в начало списка. Этот указатель имеет тип, указанный в параметре шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="removetail"></a>CTypedPtrList::RemoveTail  
 Удаляет элемент с конца списка и возвращает его.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, определяющий тип элементов, хранящихся в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель ранее в конце списка. Этот указатель имеет тип, указанный в параметре шаблона *ТИПА*.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
##  <a name="setat"></a>CTypedPtrList::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 **ПОЗИЦИИ** задаваемого элемента.  
  
 *ТИП*  
 Тип элементов, хранящихся в списке базовых классов.  
  
 `newElement`  
 Указатель на объект для записи в список.  
  
### <a name="remarks"></a>Примечания  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. `SetAt`Записывает указателя на объект в указанной позиции в списке.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Дополнительные примечания см. в разделе [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CPtrList](../../mfc/reference/cptrlist-class.md)   
 [Класс CObList](../../mfc/reference/coblist-class.md)
