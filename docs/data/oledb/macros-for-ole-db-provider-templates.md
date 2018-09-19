---
title: Макросы для шаблонов поставщика OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
- BEGIN_PROPERTY_SET
- BEGIN_PROPERTY_SET_EX
- BEGIN_PROPSET_MAP
- CHAIN_PROPERTY_SET
- END_PROPERTY_SET
- END_PROPSET_MAP
- PROPERTY_INFO_ENTRY
- PROPERTY_INFO_ENTRY_EX
- PROPERTY_INFO_ENTRY_VALUE
- BEGIN_PROVIDER_COLUMN_MAP
- END_PROVIDER_COLUMN_MAP
- PROVIDER_COLUMN_ENTRY
- PROVIDER_COLUMN_ENTRY_FIXED
- PROVIDER_COLUMN_ENTRY_GN
- PROVIDER_COLUMN_ENTRY_LENGTH
- PROVIDER_COLUMN_ENTRY_STR
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
- PROVIDER_COLUMN_ENTRY_WSTR
- BEGIN_SCHEMA_MAP
- END_SCHEMA_MAP
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
- BEGIN_PROPERTY_SET macro
- BEGIN_PROPERTY_SET_EX macro
- BEGIN_PROPSET_MAP macro
- CHAIN_PROPERTY_SET macro
- END_PROPERTY_SET macro
- END_PROPSET_MAP macro
- PROPERTY_INFO_ENTRY macro
- PROPERTY_INFO_ENTRY_EX macro
- PROPERTY_INFO_ENTRY_VALUE macro
- BEGIN_PROVIDER_COLUMN_MAP macro
- END_PROVIDER_COLUMN_MAP macro
- PROVIDER_COLUMN_ENTRY macro
- PROVIDER_COLUMN_ENTRY_FIXED macro
- PROVIDER_COLUMN_ENTRY_GN macro
- PROVIDER_COLUMN_ENTRY_LENGTH macro
- PROVIDER_COLUMN_ENTRY_STR macro
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
- PROVIDER_COLUMN_ENTRY_WSTR macro
- BEGIN_SCHEMA_MAP macro
- END_SCHEMA_MAP macro
- SCHEMA_ENTRY macro
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8953b277ff5512e71b3821d6f1f32bc897322d8c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100504"
---
# <a name="macros-for-ole-db-provider-templates"></a>Макросы для шаблонов поставщика OLE DB

Макросы шаблонов поставщик данных OLE DB предоставляют функции в следующих категориях:  
  
## <a name="property-set-map-macros"></a>Макросы сопоставления набора свойств  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](#begin_property_set)|Отмечает начало набора свойств.|  
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Отмечает начало набора свойств.|  
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Отмечает начало свойства набор, можно скрывать или определенные за пределами области поставщика.|  
|[CHAIN_PROPERTY_SET](#chain_property_set)|Группы свойств в цепочку.|  
|[END_PROPERTY_SET](#end_property_set)|Помечает конец набор свойств.|  
|[END_PROPSET_MAP](#end_propset_map)|Помечает конец сопоставление набора свойств.|  
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Задает указанное свойство в свойстве присвоено значение по умолчанию.|  
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Задает указанное свойство в свойстве, указанные вами значение. Также позволяет задать параметры и флаги.|  
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Задает указанное свойство в свойстве, указанные вами значение.|  
  
## <a name="column-map-macros"></a>Макросы сопоставления столбцов  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Отмечает начало карты записей столбцов поставщика.|  
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Помечает конец карты записей столбцов поставщика.|  
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Представляет конкретного столбца, поддерживаемых поставщиком.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Представляет конкретного столбца, поддерживаемых поставщиком. Можно указать тип данных столбца.|  
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Представляет конкретного столбца, поддерживаемых поставщиком. Можно указать размер столбца, тип данных, точность, масштаб и GUID набора строк схемы.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Представляет конкретного столбца, поддерживаемых поставщиком. Можно указать размер столбца.|  
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Представляет конкретного столбца, поддерживаемых поставщиком. Предполагается, что столбец имеет тип строки.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Представляет конкретного столбца, поддерживаемых поставщиком. PROVIDER_COLUMN_ENTRY_LENGTH, например, но также позволяет указать тип данных столбца, а также размер.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Представляет конкретного столбца, поддерживаемых поставщиком. Предполагается, что тип столбца — строка символов Юникода.|  
  
## <a name="schema-rowset-macros"></a>Макросы схемы набора строк  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Отмечает начало карты схемы.|  
|[END_SCHEMA_MAP](#end_schema_map)|Помечает конец карте схемы.|  
|[SCHEMA_ENTRY](#schema_entry)|Связывает GUID с классом.|  

## <a name="requirements"></a>Требования  

**Заголовок:** atldb.h  

### <a name="begin_property_set"></a> BEGIN_PROPERTY_SET

Отмечает начало свойства задайте в свойстве сопоставлением набора.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PROPERTY_SET(guid)  
```  
  
#### <a name="parameters"></a>Параметры  

*Идентификатор GUID*<br/>
[in] Свойство GUID.  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_property_set_ex"></a> BEGIN_PROPERTY_SET_EX

Отмечает начало свойства задайте в свойстве сопоставлением набора.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)  
```  
  
#### <a name="parameters"></a>Параметры  

*Идентификатор GUID*<br/>
[in] Свойство GUID.  
  
*flags*<br/>
[in] UPROPSET_HIDDEN любые наборы свойств, которые вы не хотите предоставлять или UPROPSET_PASSTHROUGH для поставщика, предоставление доступа к свойствам, определенные за пределами области поставщика.  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_propset_map"></a> BEGIN_PROPSET_MAP

Знаки начала свойства можно настроить записи карты.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PROPSET_MAP(Class)  
```  
  
#### <a name="parameters"></a>Параметры  

*Класс*<br/>
[in] Указывается класс, в котором значение этого свойства. Набор свойств можно задать следующие объекты OLE DB.  
  
- [Объекты источника данных](/previous-versions/windows/desktop/ms721278\(v=vs.85\))  
  
- [Объекты сеанса](/previous-versions/windows/desktop/ms711572\(v=vs.85\))  
  
- [Команды](/previous-versions/windows/desktop/ms724608\(v=vs.85\))  
  
#### <a name="example"></a>Пример  

Ниже приведен пример карты набора свойств.  
  
[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  

### <a name="chain_property_set"></a> CHAIN_PROPERTY_SET

Этот макрос объединяются в цепочку группы свойств.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
CHAIN_PROPERTY_SET(ChainClass)  
```  
  
#### <a name="parameters"></a>Параметры  

*ChainClass*<br/>
[in] Имя класса для свойства цепочки. Это класс, созданный программой мастер проектов ATL, который уже содержит схему (например, сеанса, команды или данные исходного объекта класса).  
  
#### <a name="remarks"></a>Примечания  

Можно привязать набор свойств от другого класса, чтобы ваш собственный класс, а затем доступ к свойствам непосредственно из вашего класса.  
  
> [!CAUTION]
>  Используйте этот макрос только в случае необходимости. Неправильное использование может привести к потребителя к сбою проверка на совместимость OLE DB.  

### <a name="end_property_set"></a> END_PROPERTY_SET

Помечает конец набор свойств.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_PROPERTY_SET(guid)  
```  
  
#### <a name="parameters"></a>Параметры  

*Идентификатор GUID*<br/>
[in] Свойство GUID.  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="end_propset_map"></a> END_PROPSET_MAP

Метки в конец свойства набора записей карты.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_PROPSET_MAP()  
```  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry"></a> PROPERTY_INFO_ENTRY

Представляет конкретное свойство в наборе свойств.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROPERTY_INFO_ENTRY(dwPropID)  
```  
  
#### <a name="parameters"></a>Параметры  

*dwPropID*<br/>
[in] Объект [DBPROPID](/previous-versions/windows/desktop/ms723882\(v=vs.85\)) GUID для идентификации свойства задать значение, которое можно использовать в сочетании со свойством.  
  
#### <a name="remarks"></a>Примечания  

Этот макрос задает в качестве значения свойства типа `DWORD` значение по умолчанию, определенное в ATLDB.H. Чтобы задать свойству нужное вам значение, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md). Чтобы задать `VARTYPE` и [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342\(v=vs.85\)) для свойства, в то же время, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry_ex"></a> PROPERTY_INFO_ENTRY_EX

Представляет конкретное свойство в наборе свойств.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)  
```  
  
#### <a name="parameters"></a>Параметры  

*dwPropID*<br/>
[in] Объект [DBPROPID](/previous-versions/windows/desktop/ms723882\(v=vs.85\)) GUID для идентификации свойства задать значение, которое можно использовать в сочетании со свойством.  
  
*vt*<br/>
[in] `VARTYPE` Этой записи свойства. (Определяется в файле wtypes.h)  
  
*dwFlags*<br/>
[in] Объект [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342\(v=vs.85\)) значение, описывающее эту запись свойства.  
  
*значение*<br/>
[входные данные] Значение свойства с типом `DWORD`.  
  
*options*<br/>
DBPROPOPTIONS_REQUIRED или DBPROPOPTIONS_SETIFCHEAP. Как правило, поставщик не нужно задавать *параметры* так как он задан потребителем.  
  
#### <a name="remarks"></a>Примечания  

С помощью этого макроса можно напрямую указать значение свойства типа `DWORD` , а также параметры и флаги. Чтобы задать свойству значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать свойству значение по своему усмотрению без параметров или флагов, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="property_info_entry_value"></a> PROPERTY_INFO_ENTRY_VALUE

Представляет конкретное свойство в наборе свойств.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)  
```  
  
#### <a name="parameters"></a>Параметры  

*dwPropID*<br/>
[in] Объект [DBPROPID](/previous-versions/windows/desktop/ms723882\(v=vs.85\)) GUID для идентификации свойства задать значение, которое можно использовать в сочетании со свойством.  
  
*значение*<br/>
[входные данные] Значение свойства с типом `DWORD`.  
  
#### <a name="remarks"></a>Примечания  

С помощью этого макроса можно напрямую указать значение свойства типа `DWORD`. Чтобы задать свойство, значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать значение, флаги и параметры для свойства, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).  
  
#### <a name="example"></a>Пример  

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  

### <a name="begin_provider_column_map"></a> BEGIN_PROVIDER_COLUMN_MAP

Отмечает начало карты записей столбцов поставщика.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)  
```  
  
#### <a name="parameters"></a>Параметры  

*theClass*<br/>
[in] Имя класса, к которому принадлежит эта карта.  
  
#### <a name="example"></a>Пример  

Ниже приведен пример карты столбцов поставщика.  
  
[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  

### <a name="end_provider_column_map"></a> END_PROVIDER_COLUMN_MAP

Помечает конец карты записей столбцов поставщика.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_PROVIDER_COLUMN_MAP()  
```  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  

### <a name="provider_column_entry"></a> PROVIDER_COLUMN_ENTRY

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*Член*<br/>
[in] Переменная-член в `dataClass` соответствующую столбцу.  

### <a name="provider_column_entry_fixed"></a> PROVIDER_COLUMN_ENTRY_FIXED

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*dbType*<br/>
[in] Тип данных в [DBTYPE](/previous-versions/windows/desktop/ms711251\(v=vs.85\)).  
  
*Член*<br/>
[in] Переменная-член в `dataClass` , где хранятся данные.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать тип данных столбца.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  

### <a name="provider_column_entry_gn"></a> PROVIDER_COLUMN_ENTRY_GN

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*flags*<br/>
[in] Указывает, каким образом данные возвращаются. См. в разделе `dwFlags` описание в [структуры DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)).  
  
*colSize*<br/>
[in] Размер столбца.  
  
*dbType*<br/>
[in] Указывает тип данных значения. См. в разделе `wType` описание в [структуры DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)).  
  
*precision*<br/>
[in] Указывающее точность для использования при получении данных, если *dbType* DBTYPE_NUMERIC или DBTYPE_DECIMAL. См. в разделе `bPrecision` описание в [структуры DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)).  
  
*Масштаб*<br/>
[in] Указывает шкалу для использования при получении данных, если тип dbType DBTYPE_NUMERIC или DBTYPE_DECIMAL. См. в разделе `bScale` описание в [структуры DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)).  
  
*Идентификатор GUID*<br/>
GUID набора строк схемы. См. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) в *Справочник программиста OLE DB по* список наборов строк схемы и их идентификаторы GUID.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать размер столбца, тип данных, точность, масштаб и GUID набора строк схемы.  

### <a name="provider_column_entry_length"></a> PROVIDER_COLUMN_ENTRY_LENGTH

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*size*<br/>
[in] Размер столбца в байтах.  
  
*Член*<br/>
[in] Переменная-член в `dataClass` , где хранятся данные столбца.  
  
#### <a name="remarks"></a>Примечания  

Позволяет указать размер столбца.  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md). 

### <a name="provider_column_entry_str"></a> PROVIDER_COLUMN_ENTRY_STR

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*Член*<br/>
[in] Переменная-член в классе данных, в которой хранятся данные.  
  
#### <a name="remarks"></a>Примечания  

Используйте этот макрос, если столбец данных предполагается, что [DBTYPE_STR](/previous-versions/windows/desktop/ms711251\(v=vs.85\)).  
  
#### <a name="example"></a>Пример  

См. в разделе [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).   

### <a name="provider_column_entry_type_length"></a> PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*dbType*<br/>
[in] Тип данных в [DBTYPE](/previous-versions/windows/desktop/ms711251\(v=vs.85\)).  
  
*size*<br/>
[in] Размер столбца в байтах.  
  
*Член*<br/>
[in] Переменная-член в классе данных, в которой хранятся данные.  
  
#### <a name="remarks"></a>Примечания  

Аналогичную [PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) , но также позволяет указать тип данных столбца, а также размер.  

### <a name="provider_column_entry_wstr"></a> PROVIDER_COLUMN_ENTRY_WSTR

Представляет конкретного столбца, поддерживаемых поставщиком.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)  
```  
  
#### <a name="parameters"></a>Параметры  

*name*<br/>
[in] Имя столбца.  
  
*Порядковый номер*<br/>
[in] Номер столбца. Если столбец является столбцом закладки, номер столбца не должно быть 0.  
  
*Член*<br/>
[in] Переменная-член в классе данных, в которой хранятся данные.  
  
#### <a name="remarks"></a>Примечания  

Используйте этот макрос в том случае, когда данные столбца нулем строка в Юникоде, [DBTYPE_WSTR](/previous-versions/windows/desktop/ms711251\(v=vs.85\)).  

### <a name="begin_schema_map"></a> BEGIN_SCHEMA_MAP

Обозначает начало карте схемы.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
BEGIN_SCHEMA_MAP(SchemaClass);  
```  
  
#### <a name="parameters"></a>Параметры  

*SchemaClass*<br/>
Класс, содержащий Сопоставления. Как правило, это будет класс сеанса.  
  
#### <a name="remarks"></a>Примечания  

См. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) в пакете SDK для Windows, Дополнительные сведения о наборах строк схемы.  

### <a name="end_schema_map"></a> END_SCHEMA_MAP

Обозначает конец схемы.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
END_SCHEMA_MAP()  
```  
  
#### <a name="see-also"></a>См. также  

[Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)

### <a name="schema_entry"></a> SCHEMA_ENTRY

Связывает GUID с классом.  
  
#### <a name="syntax"></a>Синтаксис  
  
```cpp
SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>Параметры  

*Идентификатор GUID*<br/>
GUID набора строк схемы. См. в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) в *Справочник программиста OLE DB по* список наборов строк схемы и их идентификаторы GUID.  
  
*RowsetClass*<br/>
Класс, который будет создан для представления набора строк схемы.  
  
#### <a name="remarks"></a>Примечания  

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) можно затем запрос на карте список идентификаторов GUID, или его можно создать набор строк, если ему присваивается идентификатор GUID. Набор строк схемы `IDBSchemaRowsetImpl` создает аналогична стандартной `CRowsetImpl`-производного класса, за исключением того, он должен предоставлять `Execute` метод, который имеет следующую сигнатуру:  
  
```cpp  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
Это `Execute` функция заполняет данные набора строк. Создает мастер проектов ATL, как описано в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\)) в *Справочник программиста OLE DB по*, три начальной наборы строк схемы в проекте для каждого из трех обязательной схемы OLE DB:  
  
- DBSCHEMA_TABLES  
  
- DBSCHEMA_COLUMNS  
  
- DBSCHEMA_PROVIDER_TYPES  
  
Мастер также добавляет три соответствующие записи в карте схемы. См. в разделе [Создание поставщика OLE DB шаблона](../../data/oledb/creating-an-ole-db-provider.md) Дополнительные сведения об использовании мастера для создания поставщика.  
  
## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   