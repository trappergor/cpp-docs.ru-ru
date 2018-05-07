---
title: Класс CMapStringToString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMapStringToString [MFC], CPair
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
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a196e2f3f4641d94bbbbda57dd1471066fb1dfa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmapstringtostring-class"></a>Класс CMapStringToString
Поддерживает сопоставления объектов `CString` , зашифрованных объектами `CString` .  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>Участники  
 Функции-члены `CMapStringToString` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CObject` указатель как возвращаемое значение или «выход» параметр, функции, замените указатель `char`. Если вы видите `CObject` указатель как параметр «вход» функция замены указатель `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 , например, преобразуется в  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>Открытые структуры  
  
|name|Описание|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|Вложенную структуру, содержащую значение ключа и значения связанных строковых объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее число элементов в хэш-таблице.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает количество элементов в этой схеме.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает позицию первого элемента.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицы.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие пустой карты (нет элементов).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Находит указатель void на основе ключа указателя void. Значение указателя не сущности, которую он указывает, используется для сравнения ключей.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый `CString` на карте.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Возвращает указатель на следующий `CString` для выполнения итерации.|  
|[CMapStringToString::PLookup](#plookup)|Возвращает указатель на `CString` , значение которого совпадает с указанным значением.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой карты.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный с помощью ключа.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в сопоставление — оператор подстановки для `SetAt`.|  
  
## <a name="remarks"></a>Примечания  
 `CMapStringToString` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если карта хранится в архив с помощью перегруженных вставки ( **<<**) оператор или с `Serialize` функции-члена.  
  
 Если вам требуется дамп отдельных `CString` -  `CString` элементов, необходимо задать глубины контекста дампа 1 или больше.  
  
 Когда `CMapStringToString` объект удаляется или когда его элементы будут удалены, `CString` удаляются объекты соответствующим образом.  
  
 Дополнительные сведения о `CMapStringToString`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="cpair"></a>  CMapStringToString::CPair  
 Содержит значение ключа и значения связанных строковых объекта.  
  
### <a name="remarks"></a>Примечания  
 Это вложенную структуру в класс [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).  
  
 Структура состоит из двух полей.  
  
- **ключ** фактическое значение тип ключа.  
  
- **значение** значение связанного объекта.  
  
 Он используется для хранения значения, возвращаемые из [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), и [CMapStringToString::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Пример  
  Пример использования см. пример для [CMapStringToString::PLookup](#plookup).  
  
##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc  
 Возвращает первый элемент объекта карты.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на первую запись в схеме; в разделе [CMapStringToString::CPair](#cpair). Если сопоставление пусто, значение равно `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция возвращает указатель на первый элемент в объекте map.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc  
 Извлекает элемент карты, на который указывает `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>Параметры  
 *pAssoc*  
 Указывает на запись сопоставления, который возвращается предыдущим вызовом [PGetNextAssoc](#pgetnextassoc) или [PGetFirstAssoc](#pgetfirstassoc) вызова.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующую запись в сопоставление; в разделе [CMapStringToString::CPair](#cpair). Если элемент является последним в схеме, это значение равно **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод служит для перебора всех элементов в объекте map. Получение первого элемента с помощью вызова `PGetFirstAssoc` и затем выполните итерацию через схему при последующих вызовах для `PGetNextAssoc`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>  CMapStringToString::PLookup  
 Ищет значение сопоставлен с данным ключом.  
  
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
 Этот метод используется для поиска элемента карты с ключом, который совпадает с указанным ключом.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



