---
title: "Класс cObList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs: C++
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8d4c14ebe2c2e9cb143d8c08ab2e8170a7cd0f5c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="coblist-class"></a>Класс cObList
упорядоченные списки неуникальные fSupports `CObject` указатели доступны последовательно или по значению указателей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObList::CObList](#coblist)|Создает пустой список с `CObject` указатели.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) в начало списка (делает нового заголовка).|  
|[CObList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) заключительного списка (делает новый заключительного).|  
|[CObList::Find](#find)|Возвращает положение элемента, заданного значением указателя.|  
|[CObList::FindIndex](#findindex)|Возвращает позицию указанного отсчитываемый от нуля индекс элемента.|  
|[CObList::GetAt](#getat)|Возвращает элемент в заданной позиции.|  
|[CObList::GetCount](#getcount)|Возвращает количество элементов в этом списке.|  
|[CObList::GetHead](#gethead)|Возвращает элемент head списка (не может быть пустым).|  
|[CObList::GetHeadPosition](#getheadposition)|Возвращает позицию в ведущий элемент списка.|  
|[CObList::GetNext](#getnext)|Получает следующий элемент для выполнения итерации.|  
|[CObList::GetPrev](#getprev)|Возвращает предыдущий элемент для выполнения итерации.|  
|[CObList::GetSize](#getsize)|Возвращает количество элементов в этом списке.|  
|[CObList::GetTail](#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CObList::GetTailPosition](#gettailposition)|Возвращает позицию заключительного элемента списка.|  
|[CObList::InsertAfter](#insertafter)|Вставляет новый элемент после заданной позиции.|  
|[CObList::InsertBefore](#insertbefore)|Вставляет новый элемент до заданной позиции.|  
|[CObList::IsEmpty](#isempty)|Проверяет условие пустой список (нет элементов).|  
|[CObList::RemoveAll](#removeall)|Удаляет все элементы из списка.|  
|[CObList::RemoveAt](#removeat)|Удаляет элемент из этого списка в указанной позиции.|  
|[CObList::RemoveHead](#removehead)|Удаляет элемент в начало списка.|  
|[CObList::RemoveTail](#removetail)|Удаляет элемент с конца списка.|  
|[CObList::SetAt](#setat)|Задает элемент в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 `CObList`списки ведут себя как взаимосвязанные списки.  
  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Можно использовать **ПОЗИЦИИ** переменной как итератор для последовательного прохождения список и как закладки, чтобы место хранения. Позиция в массиве не совпадает с помощью индекса, однако.  
  
 Вставка элемента является очень быстро в начало списка, обозначаемый и в известном **ПОЗИЦИИ**. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может быть медленным, если список слишком длинный.  
  
 `CObList` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Если список `CObject` указатели хранится в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, каждый `CObject` элемент сериализуется в свою очередь.  
  
 Если вам требуется дамп отдельных `CObject` элементов в списке, необходимо задать глубины контекста дампа 1 или больше.  
  
 Когда `CObList` объект удаляется или когда его элементы удаляются, только `CObject` удаляются указатели, не объекты, они ссылаются.  
  
 Можно создать производные классы из `CObList`. Новый класс список, предназначенный для хранения указателей для объектов, производных от `CObject`, добавляет новые элементы данных и новые функции-члены. Обратите внимание, что этот список не является строго типизированным, так как она допускает вставку любого `CObject` указателя.  
  
> [!NOTE]
>  Необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации производного класса, если вы собираетесь сериализации списка.  
  
 Дополнительные сведения об использовании `CObList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="addhead"></a>CObList::AddHead  
 Добавляет новый элемент или список элементов в заголовке этого списка.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `newElement`  
 `CObject` Указатель для добавления в этот список.  
  
 `pNewList`  
 Указатель на другую `CObList` списка. Элементы в `pNewList` будет добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::AddHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ AddHead (void\***  `newElement` **);**<br /><br /> **void AddHead (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ AddHead (const CString &** `newElement` **);**<br /><br /> **ПОЗИЦИЯ AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList\***  `pNewList` **);**|  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустым, перед выполнением операции.  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>CObList::AddTail  
 Добавляет новый элемент или список элементов заключительного этого списка.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `newElement`  
 `CObject` Указатель для добавления в этот список.  
  
 `pNewList`  
 Указатель на другую `CObList` списка. Элементы в `pNewList` будет добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустым, перед выполнением операции.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::AddTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**AddTail ПОЗИЦИИ (void\***  `newElement` **);**<br /><br /> **void AddTail (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**AddTail ПОЗИЦИИ (const CString &** `newElement` **);**<br /><br /> **AddTail ПОЗИЦИИ (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList\***  `pNewList` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>CObList::CObList  
 Создает пустой `CObject` список указателей.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Гранулярность выделения памяти для расширения списка.  
  
### <a name="remarks"></a>Примечания  
 При увеличении списке память выделяется в единицах `nBlockSize` записей. Если происходит сбой выделения памяти, `CMemoryException` возникает исключение.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::CObList`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Пример  
  Ниже приведен полный листинг `CObject`-производного класса `CAge` используется во всех примерах коллекции:  
  
 [!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 Ниже приведен пример `CObList` использования конструктора:  
  
 [!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>CObList::Find  
 Выполняет поиск в списке последовательно, чтобы найти первый `CObject` указателя, совпадающий с указанным `CObject` указателя.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `searchValue`  
 Указатель на объект можно найти в этом списке.  
  
 `startAfter`  
 Начальное положение поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если объект не найден.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что сравниваются значения указателя, а не содержимое объектов.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::Find`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Найти ПОЗИЦИИ (void\***  `searchValue` **, положение** `startAfter` **= NULL) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Найти ПОЗИЦИИ (LPCTSTR** `searchValue` **, положение** `startAfter` **= NULL) const;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>CObList::FindIndex  
 Использует значение `nIndex` как индекс в списке.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента списка, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если `nIndex` слишком велик. (Платформа создает утверждение, если `nIndex` является отрицательным значением.)  
  
### <a name="remarks"></a>Примечания  
 Начинает последовательного сканирования с начало списка, остановка на  *n* элемент th.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::FindIndex`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ FindIndex (INT_PTR** `nIndex` **) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ FindIndex (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>CObList::GetAt  
 Переменная типа **ПОЗИЦИИ** является ключом для списка.  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *положение*  
 Объект **ПОЗИЦИИ** значение, возвращенное предыдущим `GetHeadPosition` или **найти** вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. `GetAt`Извлекает `CObject` указатель, связанный с заданной позиции.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (ПОЗИЦИЯ** *позиции* **) const;**<br /><br /> **void\*& GetAt (ПОЗИЦИЯ** *позиции* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (ПОЗИЦИЯ** *позиции* **) const;**<br /><br /> **CString & GetAt (ПОЗИЦИЯ** *позиции* **);**|  
  
### <a name="example"></a>Пример  
  Далее приведен пример [FindIndex](#findindex).  
  
##  <a name="getcount"></a>CObList::GetCount  
 Возвращает количество элементов в списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение, представляющее количество элементов.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetCount`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetCount)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>CObList::GetHead  
 Возвращает `CObject` указатель, который представляет элемент head этого списка.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель **const CObList**, затем `GetHead` возвращает `CObject` указателя. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель с `CObList`, затем `GetHead` возвращает ссылку на `CObject` указателя. Это позволяет использовать слева от оператора присваивания функции и таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& () GetHead const; void\*& GetHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 Следующий пример иллюстрирует использование `GetHead` слева от оператора присваивания.  
  
 [!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>CObList::GetHeadPosition  
 Возвращает позицию в ведущий элемент этого списка.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetHeadPosition`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; ПОЗИЦИИ GetHeadPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; ПОЗИЦИИ GetHeadPosition)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>CObList::GetNext  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для `POSITION` значение на следующую запись в списке.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылку на `POSITION` значение, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNext` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetHeadPosition` или `Find`.  
  
 Необходимо убедиться, что ваш `POSITION` значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученный элемент является последним в списке, то новое значение `rPosition` равно `NULL`.  
  
 Существует возможность удалить элемент во время итерации. Далее приведен пример [RemoveAt](#removeat).  
  
> [!NOTE]
>  Начиная с MFC 8.0 изменилась const версия этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено для обеспечения соответствия стандарту c++ компилятора.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetNext`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>CObList::GetPrev  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для `POSITION` значение предыдущей записи в списке.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылку на `POSITION` значение, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetPrev` в цикле перебора в обратном порядке, если установить начальное положение, с помощью вызова `GetTailPosition` или `Find`.  
  
 Необходимо убедиться, что ваш `POSITION` значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 Если полученного элемента является первым в списке, то новое значение `rPosition` равно `NULL`.  
  
> [!NOTE]
>  Начиная с MFC 8.0 изменилась const версия этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено для обеспечения соответствия стандарту c++ компилятора.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetPrev`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>CObList::GetSize  
 Возвращает число элементов списка.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества элементов в списке.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetSize`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetSize)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>CObList::GetTail  
 Возвращает `CObject` указатель, который представляет элемент заключительного этого списка.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `GetTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& () GetTail const; void\*& GetTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>CObList::GetTailPosition  
 Возвращает положение элемента заключительного этого списка. **NULL** Если список пуст.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::GetTailPosition`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; ПОЗИЦИИ GetTailPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; ПОЗИЦИИ GetTailPosition)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>CObList::InsertAfter  
 Добавляет элемент в этот список после элемента в указанной позиции.  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *положение*  
 Значение **POSITION** , возвращенное предыдущим вызовом функции-члена `GetNext`, `GetPrev`или **Find** .  
  
 `newElement`  
 Указатель на объект для добавления в этот список.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::InsertAfter`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** это то же самое значение как *позиции* параметра.  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>CObList::InsertBefore  
 Добавляет элемент в список перед элементом в указанной позиции.  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Параметры  
 *положение*  
 Значение **POSITION** , возвращенное предыдущим вызовом функции-члена `GetNext`, `GetPrev`или **Find** .  
  
 `newElement`  
 Указатель на объект для добавления в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или извлечения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::InsertBefore`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>CObList::IsEmpty  
 Указывает, является ли этот список не содержит элементов.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот список пуст; в противном случае — 0.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::IsEmpty`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|  
  
### <a name="example"></a>Пример  
  Далее приведен пример [RemoveAll](#removeall).  
  
##  <a name="removeall"></a>CObList::RemoveAll  
 Удаляет все элементы из списка и освобождает связанные `CObList` памяти.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Если список пуст, уже ошибки не формируются.  
  
 При удалении элементов из `CObList`, удалите указателей на объекты из списка. Он будет необходимо удалить сами объекты.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::RemoveAll`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void (RemoveAll);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void (RemoveAll);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>CObList::RemoveAt  
 Удаляет указанный элемент из этого списка.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Параметры  
 *положение*  
 Позиция элемента, который требуется удалить из списка.  
  
### <a name="remarks"></a>Примечания  
 При удалении элемента из `CObList`, удалите указатель на объект из списка. Он будет необходимо удалить сами объекты.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::RemoveAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|  
  
### <a name="example"></a>Пример  
  Будьте внимательны при удалении элементов во время итерации списка. В следующем примере показан способ удаления гарантирует допустимый **ПОЗИЦИИ** значение для [GetNext](#getnext).  
  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>CObList::RemoveHead  
 Удаляет элемент в начало списка и возвращает указатель на него.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CObject` Указатель ранее в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveHead`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::RemoveHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* (RemoveHead);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>CObList::RemoveTail  
 Удаляет элемент с конца списка и возвращает указатель на него.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект, который был в конце списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не является пустой, перед вызовом `RemoveTail`. Если список пуст, подтверждает отладочной версии библиотеки классов Microsoft Foundation. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::RemoveTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* (RemoveTail);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>CObList::SetAt  
 Задает элемент в заданной позиции.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 **ПОЗИЦИИ** задаваемого элемента.  
  
 `newElement`  
 `CObject` Указатель на запись в список.  
  
### <a name="remarks"></a>Примечания  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Это не то же, что индекс и не может работать с **ПОЗИЦИИ** значение самостоятельно. `SetAt`Записывает `CObject` указатель на указанной позиции в списке.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CObList::SetAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (ПОЗИЦИЯ** `pos` **, const CString &** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (ПОЗИЦИЯ** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CStringList](../../mfc/reference/cstringlist-class.md)   
 [Класс CPtrList](../../mfc/reference/cptrlist-class.md)
