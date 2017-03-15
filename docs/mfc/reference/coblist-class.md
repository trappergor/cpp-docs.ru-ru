---
title: "Класс cObList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], lists of
- CObList class
- lists, object
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
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
ms.openlocfilehash: dc95f76be56f00f4779724facaf668a72b3d5ed6
ms.lasthandoff: 02/24/2017

---
# <a name="coblist-class"></a>Класс cObList
упорядоченные списки неуникальных fSupports `CObject` указатели доступны последовательно или по значению указателей.  
  
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
|[CObList::AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) конца списка (делает новый заключительного фрагмента).|  
|[CObList::Find](#find)|Возвращает положение элемента, заданного значением указателя.|  
|[CObList::FindIndex](#findindex)|Возвращает позицию указанного отсчитываемый от нуля индекс элемента.|  
|[CObList::GetAt](#getat)|Возвращает элемент в заданной позиции.|  
|[CObList::GetCount](#getcount)|Возвращает количество элементов в этом списке.|  
|[CObList::GetHead](#gethead)|Возвращает элемент заголовка списка (не может быть пустым).|  
|[CObList::GetHeadPosition](#getheadposition)|Возвращает позицию головной элемент списка.|  
|[CObList::GetNext](#getnext)|Получает следующий элемент для итерации.|  
|[CObList::GetPrev](#getprev)|Возвращает предыдущий элемент для итерации.|  
|[CObList::GetSize](#getsize)|Возвращает количество элементов в этом списке.|  
|[CObList::GetTail](#gettail)|Возвращает элемент заключительного списка (не может быть пустым).|  
|[CObList::GetTailPosition](#gettailposition)|Возвращает позицию заключительного элемента списка.|  
|[CObList::InsertAfter](#insertafter)|Вставляет новый элемент после заданной позиции.|  
|[CObList::InsertBefore](#insertbefore)|Вставляет новый элемент до заданной позиции.|  
|[CObList::IsEmpty](#isempty)|Проверяет условие пустой список (нет элементов).|  
|[CObList::RemoveAll](#removeall)|Удаляет все элементы из списка.|  
|[CObList::RemoveAt](#removeat)|Удаляет элемент из списка, в заданном порядке.|  
|[CObList::RemoveHead](#removehead)|Удаляет элемент в начало списка.|  
|[CObList::RemoveTail](#removetail)|Удаляет элемент из конца списка.|  
|[CObList::SetAt](#setat)|Задает элемент в заданной позиции.|  
  
## <a name="remarks"></a>Примечания  
 `CObList`списки поведению взаимосвязанные списки.  
  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Можно использовать **ПОЗИЦИИ** переменной как итератор для последовательного прохождения список и как закладки, чтобы место хранения. Позиция не совпадает с индекса, однако.  
  
 Вставка элемента очень быстро в начало списка, обозначаемый и известном **положение**. Последовательный поиск необходим для поиска элемента по значению или индексу. Поиск может быть медленным, если список длинный.  
  
 `CObList` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Если список `CObject` указатели сохраняется в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, каждый из которых `CObject` элемент сериализуется в свою очередь.  
  
 Если вам требуется дамп отдельных `CObject` элементов в списке, необходимо задать глубины контекста дампа 1 или больше.  
  
 При `CObList` объект удаляется или когда его элементы удаляются, только `CObject` удаляются указатели, не объекты, они ссылаются.  
  
 Вы можете создавать собственные производные классы из `CObList`. Новый класс списка, предназначенных для хранения указателей для объектов, производных от `CObject`, добавляет новые члены данных и новые функции-члены. Обратите внимание, что полученный список не является строго типизированным, так как он позволяет выполнять вставку любого `CObject` указателя.  
  
> [!NOTE]
>  Необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации данного производного класса, если требуется сериализовать в списке.  
  
 Дополнительные сведения об использовании `CObList`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="a-nameaddheada--coblistaddhead"></a><a name="addhead"></a>CObList::AddHead  
 Добавляет новый элемент или список элементов в заголовке этого списка.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `newElement`  
 `CObject` Указатель для добавления в этот список.  
  
 `pNewList`  
 Указатель на другую `CObList` списка. Элементы в `pNewList` будут добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::AddHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЛОЖЕНИЕ AddHead (void\* ** `newElement` **);**<br /><br /> **void AddHead (CPtrList\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЛОЖЕНИЕ AddHead (const CString &** `newElement` **);**<br /><br /> **ПОЛОЖЕНИЕ AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList\* ** `pNewList` **);**|  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустой перед операцией.  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#89;](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="a-nameaddtaila--coblistaddtail"></a><a name="addtail"></a>CObList::AddTail  
 Добавляет новый элемент или список элементов в конец списка.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>Параметры  
 `newElement`  
 `CObject` Указатель для добавления в этот список.  
  
 `pNewList`  
 Указатель на другую `CObList` списка. Элементы в `pNewList` будут добавляться в этот список.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает первую версию **ПОЗИЦИИ** значение вставленный элемент.  
  
### <a name="remarks"></a>Примечания  
 Список может быть пустой перед операцией.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::AddTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**AddTail ПОЗИЦИИ (void\* ** `newElement` **);**<br /><br /> **void AddTail (CPtrList\* ** `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**AddTail ПОЗИЦИИ (const CString &** `newElement` **);**<br /><br /> **AddTail ПОЗИЦИИ (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList\* ** `pNewList` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#90;](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="a-namecoblista--coblistcoblist"></a><a name="coblist"></a>CObList::CObList  
 Создает пустой `CObject` список указателей.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Гранулярность выделения памяти для расширения списка.  
  
### <a name="remarks"></a>Примечания  
 По мере роста списка, память выделяется в единицах `nBlockSize` записей. Если происходит сбой выделения памяти, `CMemoryException` возникает исключение.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::CObList`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Пример  
  Ниже приведен перечень `CObject`-производный класс `CAge` используется во всех примерах коллекции:  
  
 [!code-cpp[NVC_MFCCollections&#91;](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 Ниже приведен пример `CObList` использования конструктора:  
  
 [!code-cpp[NVC_MFCCollections&#92;](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="a-namefinda--coblistfind"></a><a name="find"></a>CObList::Find  
 Выполняет поиск в списке последовательно, чтобы найти первый `CObject` указателя, совпадающий с указанным ключом `CObject` указателя.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `searchValue`  
 Указатель объекта, найденному в этом списке.  
  
 `startAfter`  
 Начальное положение поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если объект не найден.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что указатель значения сравниваются, не содержимое объектов.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::Find`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Найти ПОЗИЦИИ (void\* ** `searchValue` **, положение** `startAfter` **= NULL) константу;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Найти ПОЗИЦИИ (LPCTSTR** `searchValue` **, положение** `startAfter` **= NULL) константу;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#93;](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="a-namefindindexa--coblistfindindex"></a><a name="findindex"></a>CObList::FindIndex  
 Использует значение `nIndex` как индекс в списке.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Отсчитываемый от нуля индекс элемента списка, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если `nIndex` слишком велик. (Платформа создает утверждение, если `nIndex` является отрицательным.)  
  
### <a name="remarks"></a>Примечания  
 Начинает последовательного сканирования с начало списка, остановка на *n*й элемент.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::FindIndex`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЛОЖЕНИЕ FindIndex (INT_PTR** `nIndex` **) константу;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЛОЖЕНИЕ FindIndex (INT_PTR** `nIndex` **) константу;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#94;](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="a-namegetata--coblistgetat"></a><a name="getat"></a>CObList::GetAt  
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
 Не соответствует индекс, и не может работать с **ПОЗИЦИИ** значение самостоятельно. `GetAt`Извлекает `CObject` указатель, связанный с заданной позиции.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (ПОЗИЦИЯ** *позиции* **) константу;**<br /><br /> **void\*& GetAt (ПОЗИЦИЯ** *позиции* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (ПОЗИЦИЯ** *позиции* **) константу;**<br /><br /> **CString & GetAt (ПОЗИЦИЯ** *позиции* **);**|  
  
### <a name="example"></a>Пример  
  В примере показано [FindIndex](#findindex).  
  
##  <a name="a-namegetcounta--coblistgetcount"></a><a name="getcount"></a>CObList::GetCount  
 Возвращает количество элементов в этом списке.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое значение, содержащее количество элементов.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetCount`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetCount)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#95;](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="a-namegetheada--coblistgethead"></a><a name="gethead"></a>CObList::GetHead  
 Возвращает `CObject` указатель, представляющий элемент заголовка этого списка.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если список осуществляется через указатель на **const CObList**, затем `GetHead` возвращает `CObject` указателя. Это позволяет функции для использования только в правой части оператора присваивания и тем самым защищает списка от изменения.  
  
 Если список осуществляется напрямую или через указатель к `CObList`, затем `GetHead` возвращает ссылку на `CObject` указателя. Это позволяет функции для использования с обеих сторон оператора присваивания, таким образом элементы списка изменить.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `GetHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& (GetHead) const; void\*& (GetHead);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(const) CString & GetHead константу; CString & GetHead ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 В следующем примере показано использование `GetHead` в левой части оператора присваивания.  
  
 [!code-cpp[NVC_MFCCollections&#96;](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="a-namegetheadpositiona--coblistgetheadposition"></a><a name="getheadposition"></a>CObList::GetHeadPosition  
 Возвращает позицию головного элемента этого списка.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetHeadPosition`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; положение GetHeadPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; положение GetHeadPosition)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#97;](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="a-namegetnexta--coblistgetnext"></a><a name="getnext"></a>CObList::GetNext  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для `POSITION` значение следующей записи в списке.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылку на `POSITION` значение, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другие вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNext` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetHeadPosition` или `Find`.  
  
 Необходимо убедиться, что ваш `POSITION` значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Если полученный элемент является последним в списке, то новое значение `rPosition` равен `NULL`.  
  
 Можно удалить элемент во время итерации. В примере показано [RemoveAt](#removeat).  
  
> [!NOTE]
>  Начиная с MFC 8.0 изменилась const версия этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено для обеспечения соответствия стандарту c++ компилятор.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetNext`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#98;](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="a-namegetpreva--coblistgetprev"></a><a name="getprev"></a>CObList::GetPrev  
 Возвращает элемент списка, определенный `rPosition`, затем устанавливает `rPosition` для `POSITION` значение предыдущей записи в списке.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылку на `POSITION` значение, возвращенное предыдущим `GetPrev` или других вызова функции-члена.  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetPrev` в обратной итерации цикла, если установить начальное положение, с помощью вызова `GetTailPosition` или `Find`.  
  
 Необходимо убедиться, что ваш `POSITION` значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Если полученный элемент является первым в списке, затем новое значение `rPosition` равен `NULL`.  
  
> [!NOTE]
>  Начиная с MFC 8.0 изменилась const версия этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено для обеспечения соответствия стандарту c++ компилятор.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetPrev`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#99;](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="a-namegetsizea--coblistgetsize"></a><a name="getsize"></a>CObList::GetSize  
 Возвращает количество элементов списка.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в списке.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества элементов в списке.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetSize`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetSize)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#100;](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="a-namegettaila--coblistgettail"></a><a name="gettail"></a>CObList::GetTail  
 Возвращает `CObject` указатель, который представляет элемент заключительного этого списка.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 См. в описании возвращаемое значение [GetHead](#gethead).  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `GetTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& (GetTail) const; void\*& (GetTail);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(const) CString & GetTail константу; CString & GetTail ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#101;](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="a-namegettailpositiona--coblistgettailposition"></a><a name="gettailposition"></a>CObList::GetTailPosition  
 Возвращает позицию заключительного элемента этого списка. **NULL** Если список пуст.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::GetTailPosition`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const, положение GetTailPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const, положение GetTailPosition)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#102;](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="a-nameinsertaftera--coblistinsertafter"></a><a name="insertafter"></a>CObList::InsertAfter  
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
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::InsertAfter`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **InsertAfter ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** это то же самое значение как *позиции* параметр.  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#103;](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="a-nameinsertbeforea--coblistinsertbefore"></a><a name="insertbefore"></a>CObList::InsertBefore  
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
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если список пуст.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::InsertBefore`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, void\* ** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **InsertBefore ПОЗИЦИИ (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#104;](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="a-nameisemptya--coblistisempty"></a><a name="isempty"></a>CObList::IsEmpty  
 Указывает, является ли этот список не содержит элементов.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот список пуст; в противном случае — 0.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::IsEmpty`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () константу;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () константу;**|  
  
### <a name="example"></a>Пример  
  В примере показано [RemoveAll](#removeall).  
  
##  <a name="a-nameremovealla--coblistremoveall"></a><a name="removeall"></a>CObList::RemoveAll  
 Удаляет все элементы из списка и освобождает связанные `CObList` памяти.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Если список пуст, уже ошибка не выдается.  
  
 При удалении элементов из `CObList`, удалите указателей объектов из списка. Это необходимо удалить сами объекты.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveAll`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void (RemoveAll);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void (RemoveAll);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#105;](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="a-nameremoveata--coblistremoveat"></a><a name="removeat"></a>CObList::RemoveAt  
 Удаляет указанный элемент из этого списка.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Параметры  
 *положение*  
 Положение элемента, который требуется удалить из списка.  
  
### <a name="remarks"></a>Примечания  
 При удалении элемента из `CObList`, удалите указатель объекта из списка. Это необходимо удалить сами объекты.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|  
  
### <a name="example"></a>Пример  
  Будьте внимательны при удалении элементов во время итерации списка. В следующем примере показано гарантирует допустимый способ удаления **ПОЗИЦИИ** значение [GetNext](#getnext).  
  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#106;](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="a-nameremoveheada--coblistremovehead"></a><a name="removehead"></a>CObList::RemoveHead  
 Удаляет элемент в начало списка и возвращает указатель на него.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CObject` Указатель ранее в начало списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `RemoveHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveHead`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* (RemoveHead);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#107;](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="a-nameremovetaila--coblistremovetail"></a><a name="removetail"></a>CObList::RemoveTail  
 Удаляет элемент из конца списка и возвращает указатель на него.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект, который был в конце списка.  
  
### <a name="remarks"></a>Примечания  
 Необходимо убедиться, что список не пуст, перед вызовом метода `RemoveTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveTail`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* (RemoveTail);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#108;](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="a-namesetata--coblistsetat"></a><a name="setat"></a>CObList::SetAt  
 Задает элемент в заданной позиции.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 **ПОЗИЦИИ** элемента, чтобы задать.  
  
 `newElement`  
 `CObject` Указатель на запись в список.  
  
### <a name="remarks"></a>Примечания  
 Переменная типа **ПОЗИЦИИ** является ключом для списка. Не соответствует индекс, и не может работать с **ПОЗИЦИИ** значение самостоятельно. `SetAt`Записывает `CObject` указатель на указанной позиции в списке.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 В следующей таблице показаны другой член функции, которые похожи на `CObList::SetAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (ПОЗИЦИЯ** `pos` **, const CString &** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POSITION** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Пример  
  В разделе [CObList::CObList](#coblist) список `CAge` класса.  
  
 [!code-cpp[NVC_MFCCollections&#109;](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CStringList](../../mfc/reference/cstringlist-class.md)   
 [Класс CPtrList](../../mfc/reference/cptrlist-class.md)

