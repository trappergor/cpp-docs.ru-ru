---
title: "Класс CMapStringToString | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
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
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- collection classes, string mapping
- strings [C++], mapping
- strings [C++], class for mapping
- CMapStringToString class
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
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
ms.openlocfilehash: 58ca2023d57c2865dadc8dfab304aab2fa39a96b
ms.lasthandoff: 02/24/2017

---
# <a name="cmapstringtostring-class"></a>Класс CMapStringToString
Поддерживает сопоставления объектов `CString` , зашифрованных объектами `CString` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>Члены  
 Функции-члены `CMapStringToString` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CObject` указатель как возвращаемое значение или «выходной» параметр, функции Заменить указатель `char`. Если вы видите `CObject` указатель в качестве параметра «вход» функции Заменить указатель `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 , например, преобразуется в  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>Открытые структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|Вложенные структура, содержащая значение ключа и значения связанных строковых объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает количество элементов в эту карту.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Получает следующий элемент для итерации.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает количество элементов в эту карту.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает позицию первого элемента.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицы.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указатель void. Значение указателя, а не сущности, на которую он указывает, используется для сравнения ключей.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый `CString` на карте.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Возвращает указатель на следующий `CString` для итерации.|  
|[CMapStringToString::PLookup](#plookup)|Возвращает указатель на `CString` , значение которого совпадает с указанным значением.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой карты.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент с указанным ключом.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в схеме; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 `CMapStringToString` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если карта хранится в архив с помощью перегруженных вставки ( ** << **) оператор или с `Serialize` функции-члена.  
  
 Если вам требуется дамп отдельных `CString` -  `CString` элементов, необходимо задать глубины контекста дампа 1 или больше.  
  
 Когда `CMapStringToString` удалить объект, или при удалении элементов, `CString` объекты удаляются в зависимости от необходимости.  
  
 Дополнительные сведения о `CMapStringToString`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="cpair"></a>CMapStringToString::CPair  
 Содержит значение ключа и значения связанных строковых объекта.  
  
### <a name="remarks"></a>Примечания  
 Это вложенную структуру в классе [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).  
  
 Структура состоит из двух полей:  
  
- **ключ** фактическое значение тип ключа.  
  
- **значение** значение связанного объекта.  
  
 Он используется для хранения значения, возвращаемые из [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), и [CMapStringToString::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Пример  
  Пример использования см. пример для [CMapStringToString::PLookup](#plookup).  
  
##  <a name="pgetfirstassoc"></a>CMapStringToString::PGetFirstAssoc  
 Возвращает первый элемент объекта map.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первой записи в схеме; в разделе [CMapStringToString::CPair](#cpair). Если сопоставление является пустым, значение равно `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на первый элемент в объекте map.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#73;](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc  
 Извлекает элемент карты, на который указывает `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>Параметры  
 *pAssoc*  
 Указывает запись сопоставления, возвращенная предыдущим [PGetNextAssoc](#pgetnextassoc) или [PGetFirstAssoc](#pgetfirstassoc) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель следующей записи в схеме; в разделе [CMapStringToString::CPair](#cpair). Если элемент является последним в схеме, то значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для перебора всех элементов в сопоставлении. Получение первого элемента с помощью вызова `PGetFirstAssoc` и для итерации по схеме с помощью последовательных вызовов `PGetNextAssoc`.  
  
### <a name="example"></a>Пример  
  В примере показано [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMapStringToString::PLookup  
 Ищет значение сопоставляется с помощью данного ключа.  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Указатель на ключ для элемента для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель с заданным ключом.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для поиска элемента карты с ключом, который совпадает с указанным значением ключа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections&#74;](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




