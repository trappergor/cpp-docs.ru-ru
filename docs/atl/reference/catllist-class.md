---
title: "Класс CAtlList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b1ed350da625695f610980f9f48a6ae11394d3c8
ms.lasthandoff: 02/24/2017

---
# <a name="catllist-class"></a>Класс CAtlList
Этот класс предоставляет методы для создания и управления объекта списка.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>Параметры  
 `E`  
 Тип элемента.  
  
 `ETraits`  
 Код, используемый для копирования или перемещения элементов. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](#inargtype)||  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlList::CAtlList](#catllist)|Конструктор.|  
|[CAtlList:: ~ CAtlList](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlList::AddHead](#addhead)|Вызовите этот метод, чтобы добавить элемент в начало списка.|  
|[CAtlList::AddHeadList](#addheadlist)|Этот метод используется для добавления существующего списка в начало списка.|  
|[CAtlList::AddTail](#addtail)|Этот метод используется для добавления элемента в конец списка.|  
|[CAtlList::AddTailList](#addtaillist)|Этот метод используется для добавления существующего списка в конец списка.|  
|[CAtlList::AssertValid](#assertvalid)|Вызовите этот метод, чтобы убедиться, что он действителен.|  
|[CAtlList::Find](#find)|Этот метод используется для поиска в списке для указанного элемента.|  
|[CAtlList::FindIndex](#findindex)|Этот метод вызывается для получения позиции элемента, заданного значением индекса.|  
|[CAtlList::GetAt](#getat)|Этот метод используется для возврата элемента в указанной позиции в списке.|  
|[CAtlList::GetCount](#getcount)|Этот метод используется для возврата числа объектов в списке.|  
|[CAtlList::GetHead](#gethead)|Этот метод используется для возврата элемента в начало списка.|  
|[CAtlList::GetHeadPosition](#getheadposition)|Этот метод вызывается для получения позиции в начало списка.|  
|[CAtlList::GetNext](#getnext)|Этот метод используется для возврата к следующему элементу в списке.|  
|[CAtlList::GetPrev](#getprev)|Этот метод используется для возврата предыдущего элемента в списке.|  
|[CAtlList::GetTail](#gettail)|Этот метод используется для возврата элемента в конце списка.|  
|[CAtlList::GetTailPosition](#gettailposition)|Этот метод вызывается для получения позиции конца списка.|  
|[CAtlList::InsertAfter](#insertafter)|Этот метод используется для вставки нового элемента в списке после заданной позиции.|  
|[CAtlList::InsertBefore](#insertbefore)|Этот метод используется для вставки нового элемента в список до указанной позиции.|  
|[CAtlList::IsEmpty](#isempty)|Этот метод вызывается для определения, если список пуст.|  
|[CAtlList::MoveToHead](#movetohead)|Вызовите этот метод, чтобы переместить элемент в начало списка.|  
|[CAtlList::MoveToTail](#movetotail)|Вызовите этот метод, чтобы переместить элемент в конец списка.|  
|[CAtlList::RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы из списка.|  
|[CAtlList::RemoveAt](#removeat)|Этот метод вызывается для удаления одного элемента из списка.|  
|[CAtlList::RemoveHead](#removehead)|Этот метод используется для удаления элемента в начало списка.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Вызовите этот метод, чтобы удалить элемент в начало списка, не возвращая значение.|  
|[CAtlList::RemoveTail](#removetail)|Этот метод используется для удаления элемента в конце списка.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Вызовите этот метод, чтобы удалить элемент в конец списка без возврата значения.|  
|[CAtlList::SetAt](#setat)|Вызовите этот метод, чтобы задать значение элемента в заданной позиции в списке.|  
|[CAtlList::SwapElements](#swapelements)|Этот метод вызывается для замены элементов в списке.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlList` Класс поддерживает упорядоченные списки неуникальных объектов, доступные последовательно или по значению. `CAtlList`списки ведут себя как двунаправленный список. Каждый список имеет head и заключительный фрагмент, и новые элементы (или списки в некоторых случаях) можно добавлять либо конца списка, или вставляться до или после определенных элементов.  
  
 Большинство `CAtlList` метода используют значение позиции. Это значение используется методам, чтобы указать расположение фактический объем памяти, где элементы сохраняются и не рассчитываются и прогнозируемые непосредственно. Если это необходимо для доступа к *n*й элемент в списке, а метод [CAtlList::FindIndex](#findindex) возвращает соответствующее значение для указанного индекса позиции. Методы [CAtlList::GetNext](#getnext) и [CAtlList::GetPrev](#getprev) можно использовать для прохода по объектам в списке.  
  
 Дополнительные сведения о классы коллекций, доступных в ATL в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="addhead"></a>CAtlList::AddHead  
 Вызовите этот метод, чтобы добавить элемент в начало списка.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `element`  
 Новый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию для только что добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Если используется первая версия, пустой элемент создается с помощью его конструктора по умолчанию, а не его конструктор копий.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#13;](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>CAtlList::AddHeadList  
 Этот метод используется для добавления существующего списка в начало списка.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Параметры  
 `plNew`  
 Список для добавления.  
  
### <a name="remarks"></a>Примечания  
 Список, на который указывает `plNew` вставляется в начале существующего списка. В отладочных построениях, произойдет сбой утверждения, если `plNew` равен NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#14;](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>CAtlList::AddTail  
 Этот метод используется для добавления элемента в конец списка.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `element`  
 Добавляемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ПОЗИЦИЮ для только что добавленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Если используется первая версия, пустой элемент создается с помощью его конструктора по умолчанию, а не его конструктор копий. Элемент добавляется в конец списка, и поэтому теперь становится заключительного. Этот метод можно использовать с пустой список.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#15;](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>CAtlList::AddTailList  
 Этот метод используется для добавления существующего списка в конец списка.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Параметры  
 `plNew`  
 Список для добавления.  
  
### <a name="remarks"></a>Примечания  
 Список, на который указывает `plNew` вставляется после последнего элемента (если таковые имеются) в объекте списка. Последний элемент в `plNew` списке таким образом становится заключительного. В отладочных построениях, произойдет сбой утверждения, если *plNew* равен NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities №&16;](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>CAtlList::AssertValid  
 Вызовите этот метод, чтобы убедиться, что он действителен.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях Сбой утверждения происходит, если объект не является допустимым. Допустимый, пустой список необходимо иметь head и tail, указывающий значение NULL и должен иметь список, который не является пустым, head и заключительного указывает допустимые адреса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&17;](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>CAtlList::CAtlList  
 Конструктор.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 Конструктор `CAtlList` объекта. Размер блока измеряется объем памяти, выделяемый при новый элемент является обязательным. Размер блока Уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&18;](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="dtor"></a>CAtlList:: ~ CAtlList  
 Деструктор  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, включая вызов [CAtlList::RemoveAll](#removeall) для удаления всех элементов из списка.  
  
 В отладочных построениях, произойдет сбой утверждения Если список по-прежнему содержит некоторые элементы после вызова `RemoveAll`.  
  
##  <a name="find"></a>CAtlList::Find  
 Этот метод используется для поиска в списке для указанного элемента.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `element`  
 Элемент, который требуется найти в списке.  
  
 `posStartAfter`  
 Начальное положение поиска. Если значение не указано, поиск начинается с головным элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение ПОЗИЦИИ элемента, если найден, в противном случае возвращает значение NULL.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет сбой утверждения, если объект не является допустимым или `posStartAfter` значение выходит за пределы диапазона.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&19;](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>CAtlList::FindIndex  
 Этот метод вызывается для получения позиции элемента, заданного значением индекса.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `iElement`  
 Отсчитываемый от нуля индекс элемента, список обязательных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает соответствующее значение ПОЗИЦИИ, или значение NULL, если `iElement` выходит за пределы диапазона.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает ПОЗИЦИЮ соответствующее значение индекса, предоставляя доступ к *n*й элемент в списке.  
  
 В отладочных построениях Сбой утверждения происходит, если объект не является допустимым.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&20;](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>CAtlList::GetAt  
 Этот метод используется для возврата элемента в указанной позиции в списке.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ, указав конкретный элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на или копии элемента.  
  
### <a name="remarks"></a>Примечания  
 Если список **const**, `GetAt` возвращает копию элемента. Это обеспечивает метод для использования только в правой части оператора присваивания и защищает списка от изменения.  
  
 Если список не **const**, `GetAt` возвращает ссылку на элемент. Это позволяет метода, который будет использоваться с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
 В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::FindIndex](#findindex).  
  
##  <a name="getcount"></a>CAtlList::GetCount  
 Этот метод используется для возврата числа объектов в списке.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов в списке.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::Find](#find).  
  
##  <a name="gethead"></a>CAtlList::GetHead  
 Этот метод используется для возврата элемента в начало списка.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на или копию элемента, в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Если список **const**, `GetHead` возвращает копию элемент в начало списка. Это обеспечивает метод для использования только в правой части оператора присваивания и защищает списка от изменения.  
  
 Если список не **const**, `GetHead` возвращает ссылку на элемент в начало списка. Это позволяет метода, который будет использоваться с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
 В отладочных построениях Сбой утверждения происходит, если в заголовке списка указывает на значение NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::AddHead](#addhead).  
  
##  <a name="getheadposition"></a>CAtlList::GetHeadPosition  
 Этот метод вызывается для получения позиции в начало списка.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение ПОЗИЦИИ, соответствующий элемент в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Если список пуст, возвращаемое значение равно NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#21;](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="getnext"></a>CAtlList::GetNext  
 Этот метод используется для возврата к следующему элементу в списке.  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ, возвращенный предыдущим вызовом `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), или другие `CAtlList` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список **const**, `GetNext` возвращает копию следующего элемента списка. Это обеспечивает метод для использования только в правой части оператора присваивания и защищает списка от изменения.  
  
 Если список не **const**, `GetNext` возвращает ссылку на следующий элемент списка. Это позволяет метода, который будет использоваться с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Счетчик ПОЗИЦИИ `pos`, обновляется к следующему элементу в списке, или значение NULL, если нет дополнительных элементов. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::GetHeadPosition](#getheadposition).  
  
##  <a name="getprev"></a>CAtlList::GetPrev  
 Этот метод используется для возврата предыдущего элемента в списке.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ, возвращенный предыдущим вызовом `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), или другие `CAtlList` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список **const**, `GetPrev` возвращает копию элемента списка. Это обеспечивает метод для использования только в правой части оператора присваивания и защищает списка от изменения.  
  
 Если список не **const**, `GetPrev` возвращает ссылку на элемент списка. Это позволяет метода, который будет использоваться с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Счетчик ПОЗИЦИИ `pos`, обновляется до предыдущего элемента в списке, или значение NULL, если нет дополнительных элементов. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::GetTailPosition](#gettailposition).  
  
##  <a name="gettail"></a>CAtlList::GetTail  
 Этот метод используется для возврата элемента в конце списка.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на или копию элемента, в конец списка.  
  
### <a name="remarks"></a>Примечания  
 Если список **const**, `GetTail` возвращает копию элемент в начало списка. Это обеспечивает метод для использования только в правой части оператора присваивания и защищает списка от изменения.  
  
 Если список не **const**, `GetTail` возвращает ссылку на элемент в начало списка. Это позволяет метода, который будет использоваться с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
 В отладочных построениях Сбой утверждения происходит, если конец списка указывает на значение NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::AddTail](#addtail).  
  
##  <a name="gettailposition"></a>CAtlList::GetTailPosition  
 Этот метод вызывается для получения позиции конца списка.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение ПОЗИЦИИ, соответствующий элемент в конец списка.  
  
### <a name="remarks"></a>Примечания  
 Если список пуст, возвращаемое значение равно NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#22;](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="inargtype"></a>CAtlList::INARGTYPE  
 Тип, используемый, когда элемент передается в качестве входного аргумента.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>CAtlList::InsertAfter  
 Этот метод используется для вставки нового элемента в списке после заданной позиции.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ, после которого будет вставлен новый элемент.  
  
 `element`  
 Вставляемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение ПОЗИЦИИ нового элемента.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях Сбой утверждения происходит, если список недопустим, если завершается неудачей, или при попытке вставить элемент после заключительного.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#23;](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>CAtlList::InsertBefore  
 Этот метод используется для вставки нового элемента в список до указанной позиции.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 В списке перед этой ПОЗИЦИИ значение будет вставлен новый элемент.  
  
 `element`  
 Вставляемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение ПОЗИЦИИ нового элемента.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях Сбой утверждения происходит, если список недопустим, происходит сбой вставки, или при попытке вставить элемент, прежде чем заголовок.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#24;](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>CAtlList::IsEmpty  
 Этот метод вызывается для определения, если список пуст.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если список не содержит объектов, в противном случае — значение false.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#25;](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>CAtlList::MoveToHead  
 Вызовите этот метод, чтобы переместить элемент в начало списка.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ элемента, который требуется переместить.  
  
### <a name="remarks"></a>Примечания  
 Указанный элемент перемещается из ее текущей позиции в начало списка. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#26;](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>CAtlList::MoveToTail  
 Вызовите этот метод, чтобы переместить элемент в конец списка.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ элемента, который требуется переместить.  
  
### <a name="remarks"></a>Примечания  
 Указанный элемент перемещается из ее текущей позиции в конец списка. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::MoveToHead](#movetohead).  
  
##  <a name="removeall"></a>CAtlList::RemoveAll  
 Вызовите этот метод, чтобы удалить все элементы из списка.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все элементы из списка и освобождает выделенную память. В сборках отлаживает ATLASSERT возникает, если не удалены все элементы или повреждения структуры списка.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlList::RemoveAt  
 Этот метод вызывается для удаления одного элемента из списка.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ элемента, который требуется удалить.  
  
### <a name="remarks"></a>Примечания  
 Элемент, на который указывает `pos` удаляется, и память освобождается. Допускается использование `RemoveAt` для удаления начало или конец списка.  
  
 В отладочных построениях произойдет сбой утверждения, если список не является допустимым или удаление элемента приводит к удалению списка для доступа к памяти, который не является частью структуры списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#27;](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>CAtlList::RemoveHead  
 Этот метод используется для удаления элемента в начало списка.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает элемент в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Головной элемент удаляется из списка, и память освобождается. Возвращается копия элемента. В отладочных построениях Сбой утверждения происходит, если список пуст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#28;](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn  
 Вызовите этот метод, чтобы удалить элемент в начало списка, не возвращая значение.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Головной элемент удаляется из списка, и память освобождается. В отладочных построениях Сбой утверждения происходит, если список пуст.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removetail"></a>CAtlList::RemoveTail  
 Этот метод используется для удаления элемента в конце списка.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает элемент в конец списка.  
  
### <a name="remarks"></a>Примечания  
 Tail элемент удаляется из списка, и память освобождается. Возвращается копия элемента. В отладочных построениях Сбой утверждения происходит, если список пуст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#29;](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn  
 Вызовите этот метод, чтобы удалить элемент в конец списка без возврата значения.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Tail элемент удаляется из списка, и память освобождается. В отладочных построениях Сбой утверждения происходит, если список пуст.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlList::IsEmpty](#isempty).  
  
##  <a name="setat"></a>CAtlList::SetAt  
 Вызовите этот метод, чтобы задать значение элемента в заданной позиции в списке.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение ПОЗИЦИИ, соответствующий элемент, который требуется изменить.  
  
 `element`  
 Новое значение элемента.  
  
### <a name="remarks"></a>Примечания  
 Заменяет существующее значение `element`. В отладочных построениях, произойдет сбой утверждения, если `pos` равен NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#30;](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>CAtlList::SwapElements  
 Этот метод вызывается для замены элементов в списке.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pos1*  
 Первое значение ПОЗИЦИИ.  
  
 *pos2*  
 Второе значение ПОЗИЦИИ.  
  
### <a name="remarks"></a>Примечания  
 Меняет местами элементы в двух местах, указано. В отладочных построениях Сбой утверждения происходит, если значение либо позиции равен NULL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#31;](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CList-класс](../../mfc/reference/clist-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

