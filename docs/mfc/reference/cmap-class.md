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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 24f2c70210db2d0179f3234f18c3fcbd3bf093f2
ms.lasthandoff: 04/01/2017

---
# <a name="cmap-class"></a>Класс CMap
Класс коллекции словарей, который сопоставляет уникальные ключи значениям.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Параметры  
 `KEY`  
 Класс объекта, который используется как ключ для карты.  
  
 `ARG` *_* `KEY`  
 Тип данных, используемый для `KEY` аргументов; обычно ссылка `KEY`.  
  
 `VALUE`  
 Класс объекта, хранимый в сопоставлении.  
  
 `ARG` *_* `VALUE`  
 Тип данных, используемый для `VALUE` аргументов; обычно ссылка `VALUE`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-structures"></a>Открытые структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Вложенную структуру, содержащую ключевое значение и значение связанного объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Создает коллекцию, которая сопоставляет значения ключей.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Возвращает количество элементов в этой схеме.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Возвращает количество элементов в хэш-таблице.|  
|[CMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CMap::GetSize](#getsize)|Возвращает количество элементов в этой схеме.|  
|[CMap::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента.|  
|[CMap::InitHashTable](#inithashtable)|Инициализирует хэш-таблицы и ее размер.|  
|[CMap::IsEmpty](#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMap::Lookup](#lookup)|Ищет значение сопоставлен с данным ключом.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый элемент.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Возвращает указатель на следующий элемент для выполнения итерации.|  
|[CMap::PLookup](#plookup)|Возвращает указатель на ключ, значение которого совпадает с указанным значением.|  
|[CMap::RemoveAll](#removeall)|Удаляет все элементы из этой карты.|  
|[CMap::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|  
|[CMap::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CMap::operator]](#operator_at)|Вставляет элемент в сопоставление — оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 После вставки пару "ключ значение" (элемент) в сопоставление, можно эффективно извлекать и удалять пары с помощью ключа для доступа к нему. Также можно выполнять итерацию по всем элементам в схеме.  
  
 Переменная типа **ПОЗИЦИИ** используется для альтернативного доступа к записи. Можно использовать **ПОЗИЦИИ** запись «запомнить» и для итерации элементов карты. Может показаться, что эту итерацию расположен последовательно по значением ключа. Нет. Последовательность элементов, полученных не определен.  
  
 Некоторые функции-члены этого класса вызова глобальных вспомогательные функции, следует настроить для использования большинства `CMap` класса. В разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) в разделе макросы и глобальные объекты `MFC``Reference`.  
  
 `CMap`переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для поддержки сериализации и записи элементов в дамп. Если карта хранится архив с помощью `Serialize`, в свою очередь сериализуется каждого элемента карты. Реализация по умолчанию `SerializeElements` вспомогательный функция выполняет операцию побитового записи. Для сведений о сериализации указатель коллекции элементов, производных от `CObject` или другие пользовательские типы в разделе [как: создание коллекций типобезопасный](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Если вам требуется дамп диагностики отдельных элементов в карте (ключи и значения), необходимо присвоить глубины контекста дампа 1 или больше.  
  
 Если `CMap` объект удаляется или будут удалены при удалении его элементов, ключи и значения.  
  
 Карта производного класса аналогично вывода списка. См. в статье [коллекций](../../mfc/collections.md) иллюстрация производный класс списка специального назначения.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 Создает пустой карты.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Указывает гранулярность выделения памяти для расширения карты.  
  
### <a name="remarks"></a>Примечания  
 При увеличении карты в единицах выделяется память `nBlockSize` записей.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 Содержит ключевое значение и значение связанного объекта.  
  
### <a name="remarks"></a>Примечания  
 Это вложенную структуру в класс [CMap](../../mfc/reference/cmap-class.md).  
  
 Структура состоит из двух полей.  
  
- **ключ** фактическое значение тип ключа.  
  
- **значение** значение связанного объекта.  
  
 Он используется для хранения значения, возвращаемые из [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), и [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Пример  
 Пример использования см. пример для [CMap::PLookup](#plookup).  
  
##  <a name="getcount"></a>CMap::GetCount  
 Возвращает число элементов в объекте map.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество элементов  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::Lookup](#lookup).  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Определяет количество элементов в хэш-таблицу для карты.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в хэш-таблице.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
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
 Указывает ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` вызова.  
  
 *КЛЮЧ*  
 Параметр шаблона, указывающий тип ключа карты.  
  
 `rKey`  
 Указывает возвращаемый ключ полученного элемента.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающий тип значения карты.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в объекте map. Обратите внимание, что порядковый номер позиции не обязательно будет таким же, как последовательность значение ключа.  
  
 Если полученного элемента является последним в схеме, то новое значение `rNextPosition` равно **NULL**.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::SetAt](#setat).  
  
##  <a name="getsize"></a>CMap::GetSize  
 Возвращает количество элементов карты.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в карте.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод для извлечения нескольких элементов в объекте map.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 Начинает итерацию карты, возвращая **ПОЗИЦИИ** значение, которое может быть передан `GetNextAssoc` вызова.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, указывающее начальную позицию для прохода сопоставление; или **NULL** Если сопоставление пусто.  
  
### <a name="remarks"></a>Примечания  
 Порядковый номер итерации не является прогнозируемым; Таким образом «первый элемент в схеме» не имеет особой важности.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::SetAt](#setat).  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 Инициализирует хэш-таблицы.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);  
```  
  
### <a name="parameters"></a>Параметры  
 `hashSize`  
 Число записей в хэш-таблице.  
  
 `bAllocNow`  
 Если **TRUE**, выделяет хэш-таблице при инициализации; в противном случае таблица выделяется при необходимости.  
  
### <a name="remarks"></a>Примечания  
 Для наилучшей производительности размер хэш-таблицы должны быть простых чисел. Чтобы свести к минимуму конфликты, на размер должен быть примерно 20 процентов больше, чем самый большой набор ожидаемых данных.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::Lookup](#lookup).  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 Определяет, является ли пустой карты.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если эта карта не содержит элементов; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::RemoveAll](#removeall).  
  
##  <a name="lookup"></a>CMap::Lookup  
 Ищет значение сопоставлен с данным ключом.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, задающее тип `key` значение.  
  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
 *ЗНАЧЕНИЕ*  
 Указывает тип значения, которое необходимо найти.  
  
 `rValue`  
 Получает значение, поиск вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `Lookup`использует алгоритм хэширования для быстрого поиска элемента карты с ключом, который совпадает с указанным ключом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>[CMap::operator]  
 Удобный заменой `SetAt` функции-члена.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Параметры  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, задающее тип значения карты.  
  
 `ARG_KEY`  
 Параметр шаблона, указывающий тип значения ключа.  
  
 `key`  
 Ключ, используемый для извлечения значения из схемы.  
  
### <a name="remarks"></a>Примечания  
 Поэтому он может использоваться только в левой части оператора присваивания (l значение). Если ни один элемент карты с указанным ключом, создается новый элемент.  
  
 Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор, так как имеется возможность того, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элементов.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::Lookup](#lookup).  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 Возвращает первый элемент объекта карты.  
  
```  
const CPair* PGetFirstAssoc() const; 
CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первую запись в схеме; в разделе [CMap::CPair](#cpair). Если карты не содержит записей, это значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на первый элемент в объекте map.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Извлекает элемент карты, на который указывает `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Параметры  
 *pAssocRet*  
 Указывает на запись сопоставления, который возвращается предыдущим вызовом [PGetNextAssoc](#pgetnextassoc) или [CMap::PGetFirstAssoc](#pgetfirstassoc) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующую запись в сопоставление; в разделе [CMap::CPair](#cpair). Если элемент является последним в схеме, это значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для перебора всех элементов в объекте map. Получение первого элемента с помощью вызова `PGetFirstAssoc` и затем выполните итерацию через схему при последующих вызовах для `PGetNextAssoc`.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMap::PLookup  
 Находит значение сопоставлен с данным ключом.  
  
```  
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);  
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ элемента для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру ключей; в разделе [CMap::CPair](#cpair). Если совпадение не найдено, `CMap::PLookup` возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для поиска элемента карты с ключом, который совпадает с указанным ключом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>CMap::RemoveAll  
 Удаляет все значения из этой карте, вызвав функцию глобального **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Функция работает корректно, если сопоставление уже является пустым.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>CMap::RemoveKey  
 Ищет элемент карты, соответствующий заданному ключу; затем Если ключ найден, удаляет запись.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, определяющий тип ключа.  
  
 `key`  
 Ключ элемента, который требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был найден и успешно удален. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 **DestructElements** вспомогательной функции используется для удаления записи.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>CMap::SetAt  
 Основным средством для вставки элементов в сопоставлении.  
  
```  
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```  
  
### <a name="parameters"></a>Параметры  
 `ARG_KEY`  
 Параметр шаблона, задающее тип `key` параметр.  
  
 `key`  
 Задает ключ для нового элемента.  
  
 `ARG_VALUE`  
 Параметр шаблона, задающее тип `newValue` параметр.  
  
 `newValue`  
 Указывает значение нового элемента.  
  
### <a name="remarks"></a>Примечания  
 Во-первых ищется ключ. Если ключ найден, то изменяется соответствующее значение; в противном случае создается новый пара ключ значение.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections #62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)  

