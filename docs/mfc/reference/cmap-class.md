---
title: "Класс CMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- dictionary mapping class
- collection classes, dictionary mapping
- CMap class
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 680d44fe6154861d2c638697cfc9d3fbeab36cc4
ms.lasthandoff: 02/24/2017

---
# <a name="cmap-class"></a>Класс CMap
Класс коллекции словарей, который сопоставляет уникальные ключи значениям.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Параметры  
 `KEY`  
 Класс объекта, используемого в качестве ключа для сопоставления.  
  
 `ARG` *_* `KEY`  
 Тип данных, используемый для `KEY` аргументы, обычно ссылку на `KEY`.  
  
 `VALUE`  
 Класс объекта, хранимый в сопоставлении.  
  
 `ARG` *_* `VALUE`  
 Тип данных, используемый для `VALUE` аргументы, обычно ссылку на `VALUE`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-structures"></a>Открытые структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Вложенную структуру, содержащую ключевое значение и значение связанного объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Создает коллекцию, которая сопоставляет ключи значениям.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Возвращает количество элементов в эту карту.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Возвращает количество элементов в хэш-таблице.|  
|[CMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|  
|[CMap::GetSize](#getsize)|Возвращает количество элементов в эту карту.|  
|[CMap::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента.|  
|[CMap::InitHashTable](#inithashtable)|Инициализирует хэш-таблицу и указывает его размер.|  
|[CMap::IsEmpty](#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMap::Lookup](#lookup)|Ищет значение сопоставляется с помощью данного ключа.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый элемент.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Возвращает указатель на следующий элемент для итерации.|  
|[CMap::PLookup](#plookup)|Возвращает указатель на ключ, значение которого совпадает с указанным значением.|  
|[CMap::RemoveAll](#removeall)|Удаляет все элементы из этой карты.|  
|[CMap::RemoveKey](#removekey)|Удаляет элемент с указанным ключом.|  
|[CMap::SetAt](#setat)|Вставляет элемент в схеме; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CMap::operator]](#operator_at)|Вставляет элемент в карте â €» оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 После вставки пару "ключ значение" (элемент) в карту можно эффективно извлечь или удалить пары, доступ к нему с помощью клавиши. Можно также выполнить перебор всех элементов в сопоставлении.  
  
 Переменная типа **ПОЗИЦИИ** используется для альтернативного доступа для записи. Можно использовать **ПОЗИЦИИ** запись «запомнить» и итерации по карте. Можно подумать, что этой итерации последовательного значением ключа; Нет. Последовательность элементов, полученных не определено.  
  
 Некоторые функции-члены этого класса вызова глобальных вспомогательные функции, необходимо настроить для большинства случаев из `CMap` класса. В разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) макросы и глобальные объекты из раздела `MFC``Reference`.  
  
 `CMap`переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для поддержки сериализации и записи элементов в дамп. Если карта хранится архив с помощью `Serialize`, в свою очередь сериализуется каждого элемента карты. Реализация по умолчанию `SerializeElements` вспомогательный функция выполняет побитовое записи. Для сведений о сериализации указатель коллекции элементов, производных от `CObject` или другие пользовательские типы в разделе [как: сделать строго типизированную коллекцию](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Если необходимо диагностики дамп отдельных элементов в схеме (ключи и значения), необходимо задать глубины контекста дампа 1 или выше.  
  
 Если `CMap` объект удаляется или удаляются при удалении элементов, ключи и значения.  
  
 Формирование списка аналогично производного класса Map. См. в статье [коллекции](../../mfc/collections.md) иллюстрация производного класса список специального назначения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 Создает пустое сопоставление.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Задает гранулярность выделения памяти для расширения карты.  
  
### <a name="remarks"></a>Примечания  
 По мере роста карты памяти выделяется в единицах `nBlockSize` записей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#56;](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 Содержит ключевое значение и значение связанного объекта.  
  
### <a name="remarks"></a>Примечания  
 Это вложенную структуру в классе [CMap](../../mfc/reference/cmap-class.md).  
  
 Структура состоит из двух полей:  
  
- **Â Â keyÂ** фактическое значение тип ключа.  
  
- **Â Â valueÂ** значение связанного объекта.  
  
 Он используется для хранения значения, возвращаемые из [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), и [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Пример  
 Пример использования см. пример для [CMap::PLookup](#plookup).  
  
##  <a name="getcount"></a>CMap::GetCount  
 Получает число элементов в сопоставлении.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::Lookup](#lookup).  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Определяет число элементов в хэш-таблицу для карты.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в хэш-таблице.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#57;](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>CMap::GetNextAssoc  
 Извлекает элемент карты по `rNextPosition`, затем обновляет `rNextPosition` для обращения к следующему элементу в схеме.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rNextPosition`  
 Указывает ссылку на **положение** значение, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` вызова.  
  
 *КЛЮЧ*  
 Параметр шаблона, указав тип ключа карты.  
  
 `rKey`  
 Указывает возвращаемый ключ полученного элемента.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указав тип значения карты.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в сопоставлении. Обратите внимание, что порядковый номер позиции не обязательно совпадает с последовательности значение ключа.  
  
 Если полученного элемента является последним в схеме, то новое значение `rNextPosition` равен **NULL**.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::SetAt](#setat).  
  
##  <a name="getsize"></a>CMap::GetSize  
 Возвращает количество элементов карты.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в сопоставлении.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения количества элементов в сопоставлении.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 Начинает итерацию карты, возвращая **положение** значение, которое может быть передан `GetNextAssoc` вызова.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **положение** значение, указывающее начальную позицию для прохода карты; или **NULL** Если сопоставление является пустым.  
  
### <a name="remarks"></a>Примечания  
 Последовательность итерации не является прогнозируемым. Таким образом «первый элемент в сопоставлении» не имеет особой важности.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::SetAt](#setat).  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 Инициализирует хэш-таблицы.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUEÂ);  
```  
  
### <a name="parameters"></a>Параметры  
 `hashSize`  
 Число записей в хэш-таблице.  
  
 `bAllocNow`  
 Если **TRUE**, выделяет хэш-таблице при инициализации; в противном случае выделяется таблицы при необходимости.  
  
### <a name="remarks"></a>Примечания  
 Для наилучшей производительности размер хэш-таблицы должны быть простых чисел. Чтобы свести к минимуму конфликты, размер необходимо примерно 20% больше наибольшего ожидаемый набор данных.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::Lookup](#lookup).  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 Определяет, пуст ли карты.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта карта не содержит элементов; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::RemoveAll](#removeall).  
  
##  <a name="lookup"></a>CMap::Lookup  
 Ищет значение сопоставляется с помощью данного ключа.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, задающее тип `key` значение.  
  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
 *ЗНАЧЕНИЕ*  
 Указывает тип значения, которое требуется найти.  
  
 `rValue`  
 Получает значение, поиск вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `Lookup`использует алгоритм хэширования для быстрого поиска элемента карты с ключом, который совпадает с указанным значением ключа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>[CMap::operator]  
 Удобный заменой `SetAt` функции-члена.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Параметры  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающие тип значения карты.  
  
 `ARG_KEY`  
 Параметр шаблона, указывающие тип значения ключа.  
  
 `key`  
 Ключ, используемый для извлечения значения из карты.  
  
### <a name="remarks"></a>Примечания  
 Поэтому он может использоваться только в левой части оператора присваивания (l значение). Если ни один элемент карты с указанным ключом, создается новый элемент.  
  
 Существует не «справа» (r-значение) эквивалентен этот оператор, так как существует вероятность, что ключ может быть не найдена в схеме. Используйте `Lookup` функции-члена для извлечения элементов.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::Lookup](#lookup).  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Возвращает первый элемент объекта map.  
  
```  
const CPair* PGetFirstAssoc() const;Â CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первой записи в схеме; в разделе [CMap::CPair](#cpair). Если карта не содержит записей, то значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на первый элемент в объекте map.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#59;](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Извлекает элемент карты, на который указывает `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Параметры  
 *pAssocRet*  
 Указывает запись сопоставления, возвращенная предыдущим [PGetNextAssoc](#pgetnextassoc) или [CMap::PGetFirstAssoc](#pgetfirstassoc) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель следующей записи в схеме; в разделе [CMap::CPair](#cpair). Если элемент является последним в схеме, то значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для перебора всех элементов в сопоставлении. Получение первого элемента с помощью вызова `PGetFirstAssoc` и для итерации по схеме с помощью последовательных вызовов `PGetNextAssoc`.  
  
### <a name="example"></a>Пример  
 В примере показано [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMap::PLookup  
 Находит значение сопоставляется с помощью данного ключа.  
  
```  
const CPair* PLookup(ARG_KEY  key) const;
CPair* PLookup(Â    ARG_KEY  keyÂ);  ```  
  
### Parameters  
 `key`  
 Key for the element to be searched for.  
  
### Return Value  
 A pointer to a key structure; see [CMap::CPair](#cpair). If no match is found, `CMap::PLookup` returns `NULL`.  
  
### Remarks  
 Call this method to search for a map element with a key that exactly matches the given key.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 Removes all the values from this map by calling the global helper function **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### Remarks  
 The function works correctly if the map is already empty.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 Looks up the map entry corresponding to the supplied key; then, if the key is found, removes the entry.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the key.  
  
 `key`  
 Key for the element to be removed.  
  
### Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### Remarks  
 The **DestructElements** helper function is used to remove the entry.  
  
### Example  
 See the example for [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>  CMap::SetAt  
 The primary means to insert an element in a map.  
  
```  
void SetAt (ARG_KEY ключа, ARG_VALUE newValue;)
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the `key` parameter.  
  
 `key`  
 Specifies the key of the new element.  
  
 `ARG_VALUE`  
 Template parameter specifying the type of the `newValue` parameter.  
  
 `newValue`  
 Specifies the value of the new element.  
  
### Remarks  
 First, the key is looked up. If the key is found, then the corresponding value is changed; otherwise a new key-value pair is created.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)  

