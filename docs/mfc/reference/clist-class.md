---
title: CList-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2a84e73c165efd8f2f17e66af149e33d90395e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="clist-class"></a>CList-класс
Поддерживает упорядоченные списки неуникальных объектов, доступные последовательно или по значению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class TYPE, class ARG_TYPE = const TYPE&>  
class CList : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CList::CList](#clist)|Создает пустой упорядоченный список.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) в начало списка (делает нового заголовка).|  
|[CList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) заключительного списка (делает новый заключительного).|  
|[CList::Find](#find)|Возвращает положение элемента, заданного значением указателя.|  
|[CList::FindIndex](#findindex)|Возвращает позицию указанного отсчитываемый от нуля индекс элемента.|  
|[CList::GetAt](#getat)|Возвращает элемент в заданной позиции.|  
|[CList::GetCount](#getcount)|Возвращает количество элементов в этом списке.|  
|[CList::GetHead](#gethead)|Возвращает элемент head списка (не может быть пустым).|  
|[CList::GetHeadPosition](#getheadposition)|Возвращает позицию в ведущий элемент списка.|  
|[CList::GetNext](#getnext)|Получает следующий элемент для выполнения итерации.|  
|[CList::GetPrev](#getprev)|Возвращает предыдущий элемент для выполнения итерации.|  
|[CList::GetSize](#getsize)|Возвращает количество элементов в этом списке.|  
|[CList::GetTail](#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CList::GetTailPosition](#gettailposition)|Возвращает позицию заключительного элемента списка.|  
|[CList::InsertAfter](#insertafter)|Вставляет новый элемент после заданной позиции.|  
|[CList::InsertBefore](#insertbefore)|Вставляет новый элемент до заданной позиции.|  
|[CList::IsEmpty](#isempty)|Проверяет условие пустой список (нет элементов).|  
|[CList::RemoveAll](#removeall)|Удаляет все элементы из списка.|  
|[CList::RemoveAt](#removeat)|Удаляет элемент из этого списка в указанной позиции.|  
|[CList::RemoveHead](#removehead)|Удаляет элемент в начало списка.|  
|[CList::RemoveTail](#removetail)|Удаляет элемент с конца списка.|  
|[CList::SetAt](#setat)|Задает элемент в заданной позиции.|  
  
#### <a name="parameters"></a>Параметры  
 `TYPE`  
 Тип объекта, хранящегося в списке.  
  
 `ARG` *_* `TYPE`  
 Тип, используемый для ссылки на объекты, хранящиеся в списке. Может быть ссылкой.  
  
## <a name="remarks"></a>Примечания  
 `CList` списки ведут себя как взаимосвязанные списки.  
  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Можно использовать **ПОЗИЦИИ** переменной итератора проходить список последовательно, а закладки, чтобы место хранения. Позиция в массиве не совпадает с помощью индекса, однако.  
  
 Вставка элемента является очень быстро в начало списка, обозначаемый и в известном **ПОЗИЦИИ**. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может быть медленным, если список слишком длинный.  
  
 Если вам требуется дамп отдельных элементов в списке, необходимо задать глубины контекста дампа 1 или выше.  
  
 Некоторые функции-члены этого класса вызова глобальных вспомогательные функции, следует настроить для использования большинства `CList` класса. В разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) в разделе «Макросы и глобальные переменные».  
  
 Дополнительные сведения об использовании `CList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="addhead"></a>  CList::AddHead  
 Добавляет новый элемент или список элементов в заголовке этого списка.  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_TYPE`  
 Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).  
  
 `newElement`  
 Новый элемент.  
  
 `pNewList`  
 Указатель на другую `CList` списка. Элементы в `pNewList` будет добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустым, перед выполнением операции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CList::AddTail  
 Добавляет новый элемент или список элементов заключительного этого списка.  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_TYPE`  
 Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).  
  
 `newElement`  
 Элемент, добавляемый в список.  
  
 `pNewList`  
 Указатель на другую `CList` списка. Элементы в `pNewList` будет добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустым, перед выполнением операции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="clist"></a>  CList::CList  
 Создает пустой упорядоченный список.  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Гранулярность выделения памяти для расширения списка.  
  
### <a name="remarks"></a>Примечания  
 При увеличении списке память выделяется в единицах `nBlockSize` записей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>  CList::Find  
 Выполняет поиск в списке последовательно, чтобы найти первый элемент, совпадающий с указанным `searchValue`.  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_TYPE`  
 Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).  
  
 `searchValue`  
 Значение должно быть найдено в списке.  
  
 `startAfter`  
 Начальное положение поиска. Если значение не указано, то поиск начинается с элементом head.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если объект не найден.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CList::FindIndex  
 Использует значение `nIndex` как индекс в списке.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента списка, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если `nIndex` отрицательное или слишком велико.  
  
### <a name="remarks"></a>Примечания  
 Начинает последовательного сканирования с начало списка, остановка на *n*элемент th.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>  CList::GetAt  
 Возвращает элемент списка в заданной позиции.  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип объекта в списке.  
  
 *Положение*  
 Позиция элемента в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение `GetHead`.  
  
### <a name="remarks"></a>Примечания  
 `GetAt` Возвращает элемент (или ссылку на элемент), связанный с заданной позиции. Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. Переменная типа **ПОЗИЦИИ** является ключом для списка.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CList::GetHeadPosition](#getheadposition).  
  
##  <a name="getcount"></a>  CList::GetCount  
 Возвращает количество элементов в списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее количество элементов.  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода будет создавать один и тот же результат как [CList::GetSize](#getsize) метод.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CList::RemoveHead](#removehead).  
  
##  <a name="gethead"></a>  CList::GetHead  
 Возвращает элемент head (или ссылку на элемент head) из этого списка.  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип объекта в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список **const**, `GetHead` возвращает копию элемент в начало списка. Это позволяет использовать только в правой части оператора присваивания функции и защищает от изменения списка.  
  
 Если список не является **const**, `GetHead` возвращает ссылку на элемент в начало списка. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>  CList::GetHeadPosition  
 Возвращает позицию в ведущий элемент этого списка.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если список пуст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>  CList::GetNext  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение на следующую запись в списке.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNext`, [GetHeadPosition](#getheadposition), или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список **const**, `GetNext` возвращает копию объекта элемента списка. Это позволяет использовать только в правой части оператора присваивания функции и защищает от изменения списка.  
  
 Если список не является **const**, `GetNext` возвращает ссылку на элемент списка. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNext` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetHeadPosition` или **найти**.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученный элемент является последним в списке, то новое значение `rPosition` равно **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>  CList::GetPrev  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для **ПОЗИЦИИ** значение предыдущей записи в списке.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в списке.  
  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список **const**, `GetPrev` возвращает копию элемент в начало списка. Это позволяет использовать только в правой части оператора присваивания функции и защищает от изменения списка.  
  
 Если список не является **const**, `GetPrev` возвращает ссылку на элемент списка. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetPrev` в цикле перебора в обратном порядке, если установить начальное положение, с помощью вызова `GetTailPosition` или **найти**.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученного элемента является первым в списке, то новое значение `rPosition` равно **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>  CList::GetSize  
 Возвращает число элементов списка.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества элементов в списке.  Вызов этого метода будет создавать один и тот же результат как [CList::GetCount](#getcount) метод.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>  CList::GetTail  
 Возвращает `CObject` указатель, который представляет элемент заключительного этого списка.  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](../../mfc/reference/coblist-class.md#gethead).  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>  CList::GetTailPosition  
 Возвращает положение элемента заключительного этого списка. **NULL** Если список пуст.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если список пуст.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>  CList::InsertAfter  
 Добавляет элемент в этот список после элемента в указанной позиции.  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *Положение*  
 Значение **POSITION** , возвращенное предыдущим вызовом функции-члена `GetNext`, `GetPrev`или **Find** .  
  
 `ARG_TYPE`  
 Параметр шаблона, определяющий тип элемента списка.  
  
 `newElement`  
 Элемент, добавляемый в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **POSITION** , которое можно использовать для итерации или извлечения элемента списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>  CList::InsertBefore  
 Добавляет элемент в список перед элементом в указанной позиции.  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *Положение*  
 Значение **POSITION** , возвращенное предыдущим вызовом функции-члена `GetNext`, `GetPrev`или **Find** .  
  
 `ARG_TYPE`  
 Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).  
  
 `newElement`  
 Элемент, добавляемый в список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **POSITION** , которое можно использовать для итерации или извлечения элемента списка.  
  
### <a name="remarks"></a>Примечания  
 Если *позиция* — **NULL**, элемент вставляется в начало списка.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>  CList::IsEmpty  
 Указывает, является ли этот список не содержит элементов.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот список пуст; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>  CList::RemoveAll  
 Удаляет все элементы из списка и освобождает связанные память.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Если список пуст, уже ошибки не формируются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CList::RemoveAt  
 Удаляет указанный элемент из этого списка.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Параметры  
 *Положение*  
 Позиция элемента, который требуется удалить из списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>  CList::RemoveHead  
 Удаляет элемент в начало списка и возвращает указатель на него.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, ранее в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CList::RemoveTail  
 Удаляет элемент с конца списка и возвращает указатель на него.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Параметры  
 *ТИП*  
 Параметр шаблона, указывающий тип элементов в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, который был в конце списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>  CList::SetAt  
 Переменная типа **ПОЗИЦИИ** является ключом для списка.  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 **ПОЗИЦИИ** задаваемого элемента.  
  
 `ARG_TYPE`  
 Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).  
  
 `newElement`  
 Элемент, добавляемый в список.  
  
### <a name="remarks"></a>Примечания  
 Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. `SetAt` Записывает элемент в указанную позицию в списке.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMap](../../mfc/reference/cmap-class.md)   
 [Класс CArray](../../mfc/reference/carray-class.md)
