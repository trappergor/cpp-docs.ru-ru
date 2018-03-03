---
title: "Класс CMapStringToOb | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a840677819710247e73aa8e3bcb904be756f852
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmapstringtoob-class"></a>Класс CMapStringToOb
Класс коллекции словаря, который сопоставляет уникальные объекты `CString` с указателями `CObject` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Определяет текущее число элементов в хэш-таблице.|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CMapStringToOb::GetSize](#getsize)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента.|  
|[CMapStringToOb::HashKey](#hashkey)|Вычисляет хэш-значение указанного ключа.|  
|[CMapStringToOb::InitHashTable](#inithashtable)|Инициализирует хэш-таблицы.|  
|[CMapStringToOb::IsEmpty](#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMapStringToOb::Lookup](#lookup)|Находит указатель void на основе ключа указателя void. Значение указателя не сущности, которую он указывает, используется для сравнения ключей.|  
|[CMapStringToOb::LookupKey](#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|  
|[CMapStringToOb::RemoveAll](#removeall)|Удаляет все элементы из этой карты.|  
|[CMapStringToOb::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|  
|[CMapStringToOb::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[[CMapStringToOb::operator]](#operator_at)|Вставляет элемент в сопоставление — оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 После вставки `CString` -  `CObject*` пары (элемент) в сопоставление, можно эффективно извлекать и удалять пары, используя строку или `CString` значение в качестве ключа. Также можно выполнять итерацию по всем элементам в схеме.  
  
 Переменная типа **ПОЗИЦИИ** используется Access альтернативную запись для всех вариантов карты. Можно использовать **ПОЗИЦИИ** запись «запомнить» и для итерации элементов карты. Может показаться, что эту итерацию расположен последовательно по значением ключа. Нет. Последовательность элементов, полученных не определен.  
  
 `CMapStringToOb` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если карта хранится в архив с помощью перегруженных вставки (  **<<** ) оператор или с `Serialize` функции-члена.  
  
 Если вам требуется диагностики дамп отдельных элементов в карте ( `CString` значение и `CObject` содержимое), необходимо задать глубины контекста дампа 1 или больше.  
  
 Когда `CMapStringToOb` объект удаляется или когда его элементы будут удалены, `CString` объектов и `CObject` указатели удаляются. Объекты, упоминаемые `CObject` указатели, не удаляются.  
  
 Карта производного класса аналогично вывода списка. См. в статье [коллекций](../../mfc/collections.md) иллюстрация производный класс списка специального назначения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb  
 Создает пустой `CString`- в - `CObject*` карты.  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Указывает гранулярность выделения памяти для расширения карты.  
  
### <a name="remarks"></a>Примечания  
 При увеличении карты в единицах выделяется память `nBlockSize` записей.  
  
 В следующей таблице приведены другие члена функции, которые похожи на **CMapStringToOb:: CMapStringToOb**.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
##  <a name="getcount"></a>CMapStringToOb::GetCount  
 Определяет, сколько элементов на карте.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в этой схеме.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::GetCount`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; INT_PTR GetCount)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; INT_PTR GetCount)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; INT_PTR GetCount)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; INT_PTR GetCount)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; INT_PTR GetCount)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize  
 Определяет текущее число элементов в хэш-таблице.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов в хэш-таблице.  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::GetHashTableSize`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; UINT GetHashTableSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; UINT GetHashTableSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; UINT GetHashTableSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; UINT GetHashTableSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; UINT GetHashTableSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; UINT GetHashTableSize)**|  
  
##  <a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc  
 Извлекает элемент карты по *rNextPosition*, затем обновляет *rNextPosition* для обращения к следующему элементу в схеме.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *rNextPosition*  
 Указывает ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим **GetNextAssoc** или **GetStartPosition** вызова.  
  
 *rKey*  
 Указывает возвращаемый ключ полученного элемента (строка).  
  
 *rValue*  
 Указывает возвращаемое значение полученного элемента ( **CObject** указатель). Для получения дополнительных сведений об этом параметре см. заметки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в объекте map. Обратите внимание, что порядковый номер позиции не обязательно будет таким же, как последовательность значение ключа.  
  
 Если полученного элемента является последним в схеме, то новое значение *rNextPosition* равно **NULL**.  
  
 Для *rValue* параметр, убедитесь, что тип объекта, чтобы привести **CObject\*&**, который является то, что компилятор требует, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 Это не относится к **GetNextAssoc** для карт на основе шаблонов.  
  
 В следующей таблице приведены другие члена функции, которые похожи на **CMapStringToOb::GetNextAssoc**.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, void\* &**  *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, void\* &**  *rKey* **, WORD &** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, CString &** *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, WORD &** *rKey* **, CObject\* &**  *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (ПОЗИЦИЯ &** *rNextPosition* **, WORD &** *rKey* **, void\* &**  *rValue* **) const;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>CMapStringToOb::GetSize  
 Возвращает количество элементов карты.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в карте.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения нескольких элементов в объекте map.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::GetSize`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; INT_PTR GetSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; INT_PTR GetSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; INT_PTR GetSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; INT_PTR GetSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; INT_PTR GetSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>CMapStringToOb::GetStartPosition  
 Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextAssoc` вызова.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, указывающее начальную позицию для прохода сопоставление; или **NULL** Если сопоставление пусто.  
  
### <a name="remarks"></a>Примечания  
 Порядковый номер итерации не является прогнозируемым; Таким образом «первый элемент в схеме» не имеет особой важности.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::GetStartPosition`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; ПОЗИЦИИ GetStartPosition)**|  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMapStringToOb::GetNextAssoc](#getnextassoc).  
  
##  <a name="hashkey"></a>CMapStringToOb::HashKey  
 Вычисляет хэш-значение указанного ключа.  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, значение которого хэш вычисляться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение хэша ключа  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::HashKey`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
  
##  <a name="inithashtable"></a>CMapStringToOb::InitHashTable  
 Инициализирует хэш-таблицы.  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hashSize`  
 Число записей в хэш-таблице.  
  
 `bAllocNow`  
 Если **TRUE**, выделяет хэш-таблице при инициализации; в противном случае таблица выделяется при необходимости.  
  
### <a name="remarks"></a>Примечания  
 Для наилучшей производительности размер хэш-таблицы должны быть простых чисел. Чтобы свести к минимуму конфликты, на размер должен быть примерно 20 процентов больше, чем самый большой набор ожидаемых данных.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::InitHashTable`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
  
##  <a name="isempty"></a>CMapStringToOb::IsEmpty  
 Определяет, является ли пустой карты.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта карта не содержит элементов; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [RemoveAll](#removeall).  
  
### <a name="remarks"></a>Примечания  
 В следующей таблице приведены другие члена функции, которые похожи на **CMapStringToOb:: IsEmpty**.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|  
  
##  <a name="lookup"></a>CMapStringToOb::Lookup  
 Возвращает `CObject` указатель на основе `CString` значение.  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ строки, определяющий элемента, который требуется найти.  
  
 `rValue`  
 Указывает возвращаемое значение из элемента было вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `Lookup`алгоритм хэширования для быстрого поиска элемента карты с ключом, который точно соответствует ( `CString` значение).  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::LookUp`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Уточняющий запрос BOOL (void\***  `key` **, void\* &**  `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Уточняющий запрос BOOL (void\***  `key` **, WORD &** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Уточняющий запрос BOOL (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Уточняющий запрос BOOL (LPCTSTR** `key` **, CString &** `rValue` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Уточняющий запрос BOOL (WORD** `key` **, CObject\* &**  `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Уточняющий запрос BOOL (WORD** `key` **, void\* &**  `rValue` **) const;**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>CMapStringToOb::LookupKey  
 Возвращает ссылку на ключ, связанный с указанным значением ключа.  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ строки, определяющий элемента, который требуется найти.  
  
 `rKey`  
 Ссылка на связанный ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если ключ найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 С помощью ссылки на ключ является небезопасным, если используется после удаления связанного элемента из карты или карты был удален.  
  
 В следующей таблице приведены другие члена функции, которые похожи на **CMapStringToOb:: оставлены пустыми**.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL оставлены пустыми (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL оставлены пустыми (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
  
##  <a name="operator_at"></a>[CMapStringToOb::operator]  
 Удобный заменой `SetAt` функции-члена.  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на указатель на `CObject` объекту или **NULL** Если сопоставление пусто или `key` выходит за пределы диапазона.  
  
### <a name="remarks"></a>Примечания  
 Поэтому он может использоваться только в левой части оператора присваивания (l значение). Если ни один элемент карты с указанным ключом, создается новый элемент.  
  
 Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор, так как имеется возможность того, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элементов.  
  
 В следующей таблице приведены другие члена функции, которые похожи на **[CMapStringToOb::operator]**.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& operator [] (void\***  `key`  **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD & -оператор [] (void\***  `key`  **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator [] (lpctstr** `key`  **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & -оператор [] (lpctstr** `key`  **\);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& operator [] (word** `key`  **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator [] (word** `key`  **\);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>CMapStringToOb::RemoveAll  
 Удаляет все элементы из этого сопоставления и уничтожает `CString` основные объекты.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 `CObject` Объекты, упоминаемые в каждый раздел, не удаляются. `RemoveAll` Функции может вызвать утечку памяти, если это не гарантирует, что упоминаемая `CObject` уничтожения объектов.  
  
 Функция работает корректно, если сопоставление уже является пустым.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::RemoveAll`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void (RemoveAll);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void (RemoveAll);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void (RemoveAll);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void (RemoveAll);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void (RemoveAll);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void (RemoveAll);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>CMapStringToOb::RemoveKey  
 Ищет элемент карты, соответствующий заданному ключу; затем Если ключ найден, удаляет запись.  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Указывает строку, которая используется для просмотра карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был найден и успешно удален. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это может вызвать утечку памяти, если `CObject` объект в другом месте не удаляется.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::RemoveKey`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>CMapStringToOb::SetAt  
 Основным средством для вставки элементов в сопоставлении.  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает строку, которая является ключевым для нового элемента.  
  
 `newValue`  
 Указывает `CObject` указатель, который представляет значение нового элемента.  
  
### <a name="remarks"></a>Примечания  
 Во-первых ищется ключ. Если ключ найден, то изменяется соответствующее значение; в противном случае создается новый элемент ключ значение.  
  
 В следующей таблице приведены другие члена функции, которые похожи на `CMapStringToOb::SetAt`.  
  
|Класс|Функция-член|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void\***  `key` **, void\***  `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void\***  `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void\***  `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject\***  `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void\***  `newValue` **);**|  
  
### <a name="example"></a>Пример  
 В разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, который используется во всех примерах коллекции.  
  
 [!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 Ниже приведены результаты из этой программы.  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)   
 [Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)   
 [Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)   
 [Класс CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)   
 [Класс CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)   
 [Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)
