---
title: Макросы для шаблонов поставщика OLE DB
ms.date: 02/11/2019
f1_keywords:
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
ms.openlocfilehash: 5d29b2548102b056a21ebfccb037af3a766788ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369809"
---
# <a name="macros-for-ole-db-provider-templates"></a>Макросы для шаблонов поставщика OLE DB

Макросы-поставщик шаблонов OLE DB предлагают функциональность в следующих категориях:

## <a name="property-set-map-macros"></a>Недвижимость Установить Карта Макрос

|||
|-|-|
|[BEGIN_PROPERTY_SET](#begin_property_set)|Отмечает начало набора свойств.|
|[BEGIN_PROPERTY_SET_EX](#begin_property_set_ex)|Отмечает начало набора свойств.|
|[BEGIN_PROPSET_MAP](#begin_propset_map)|Отметки начала набора свойств, которые могут быть скрыты или определены вне сферы действия поставщика.|
|[CHAIN_PROPERTY_SET](#chain_property_set)|Цепочка групп собственности объединяет.|
|[END_PROPERTY_SET](#end_property_set)|Отметка конца набора свойств.|
|[END_PROPSET_MAP](#end_propset_map)|Отметка конца карты набора свойств.|
|[PROPERTY_INFO_ENTRY](#property_info_entry)|Устанавливает определенное свойство в свойстве, установленном значением по умолчанию.|
|[PROPERTY_INFO_ENTRY_EX](#property_info_entry_ex)|Устанавливает определенное свойство в свойстве, установленном на стоимость, предоставленную вами. Также позволяет устанавливать флаги и опции.|
|[PROPERTY_INFO_ENTRY_VALUE](#property_info_entry_value)|Устанавливает определенное свойство в свойстве, установленном на стоимость, предоставленную вами.|

## <a name="column-map-macros"></a>Колонка Карта Макрос

|||
|-|-|
|[BEGIN_PROVIDER_COLUMN_MAP](#begin_provider_column_map)|Отметки начала записи на карте столбцов поставщика.|
|[END_PROVIDER_COLUMN_MAP](#end_provider_column_map)|Отметки конца записей на карте столбцов поставщика.|
|[PROVIDER_COLUMN_ENTRY](#provider_column_entry)|Представляет определенный столбец, поддерживаемый поставщиком.|
|[PROVIDER_COLUMN_ENTRY_FIXED](#provider_column_entry_fixed)|Представляет определенный столбец, поддерживаемый поставщиком. Можно указать тип данных столбца.|
|[PROVIDER_COLUMN_ENTRY_GN](#provider_column_entry_gn)|Представляет определенный столбец, поддерживаемый поставщиком. Можно указать размер столбца, тип данных, точность, масштаб и схему rowset GUID.|
|[PROVIDER_COLUMN_ENTRY_LENGTH](#provider_column_entry_length)|Представляет определенный столбец, поддерживаемый поставщиком. Можно указать размер столбца.|
|[PROVIDER_COLUMN_ENTRY_STR](#provider_column_entry_str)|Представляет определенный столбец, поддерживаемый поставщиком. Он предполагает, что тип столбца является строкой.|
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](#provider_column_entry_type_length)|Представляет определенный столбец, поддерживаемый поставщиком. Как PROVIDER_COLUMN_ENTRY_LENGTH, но также позволяет указать тип данных столбца, а также размер.|
|[PROVIDER_COLUMN_ENTRY_WSTR](#provider_column_entry_wstr)|Представляет определенный столбец, поддерживаемый поставщиком. Он предполагает, что тип столбца является строкой символов Unicode.|

## <a name="schema-rowset-macros"></a>Схема Роусет Макрос

|||
|-|-|
|[BEGIN_SCHEMA_MAP](#begin_schema_map)|Отмечает начало карты схемы.|
|[END_SCHEMA_MAP](#end_schema_map)|Отметка конца карты схемы.|
|[SCHEMA_ENTRY](#schema_entry)|Ассоциирует GUID с классом.|

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

### <a name="begin_property_set"></a><a name="begin_property_set"></a>BEGIN_PROPERTY_SET

Отметка начала свойства, установленного на карте набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Параметры

*Guid*<br/>
(в) Свойство GUID.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_property_set_ex"></a><a name="begin_property_set_ex"></a>BEGIN_PROPERTY_SET_EX

Отметка начала свойства, установленного на карте набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPERTY_SET_EX(guid, flags)
```

#### <a name="parameters"></a>Параметры

*Guid*<br/>
(в) Свойство GUID.

*Флаги*<br/>
(в) UPROPSET_HIDDEN для любых наборов свойств, которые вы не хотите экспонировать, или UPROPSET_PASSTHROUGH для поставщика, разоблачающий свойства, определенные вне сферы действия поставщика.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_propset_map"></a><a name="begin_propset_map"></a>BEGIN_PROPSET_MAP

Отметки начала набора свойств записей карты.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROPSET_MAP(Class)
```

#### <a name="parameters"></a>Параметры

*Class*<br/>
(в) Класс, в котором указан этот набор свойств. Набор свойств может быть указан в следующих объектах OLE DB:

- [Объекты источника данных](/previous-versions/windows/desktop/ms721278(v=vs.85))

- [Объекты сеанса](/previous-versions/windows/desktop/ms711572(v=vs.85))

- [Команды](/previous-versions/windows/desktop/ms724608(v=vs.85))

#### <a name="example"></a>Пример

Вот карта набора свойств образца:

[!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]

### <a name="chain_property_set"></a><a name="chain_property_set"></a>CHAIN_PROPERTY_SET

Эта макроцепочки групп собственности объединяются.

#### <a name="syntax"></a>Синтаксис

```cpp
CHAIN_PROPERTY_SET(ChainClass)
```

#### <a name="parameters"></a>Параметры

*ЦепьКласс*<br/>
(в) Название класса для цепных свойств для. Это класс, генерируемый мастером проекта ATL, который уже содержит карту (например, класс объекта исходного кода сеанса, команды или исходного кода данных).

#### <a name="remarks"></a>Remarks

Вы можете пригоденить набор свойств от другого класса к своему классу, а затем получить доступ к свойствам непосредственно из вашего класса.

> [!CAUTION]
> Используйте этот макрос экономно. Неправильное использование может привести к тому, что потребитель может выйти из строя тестов соответствия OLE DB.

### <a name="end_property_set"></a><a name="end_property_set"></a>END_PROPERTY_SET

Отметка конца набора свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROPERTY_SET(guid)
```

#### <a name="parameters"></a>Параметры

*Guid*<br/>
(в) Свойство GUID.

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="end_propset_map"></a><a name="end_propset_map"></a>END_PROPSET_MAP

Отметки конца записей карты, установленной свойством.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROPSET_MAP()
```

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry"></a><a name="property_info_entry"></a>PROPERTY_INFO_ENTRY

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY(dwPropID)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

#### <a name="remarks"></a>Remarks

Этот макрос задает в качестве значения свойства типа `DWORD` значение по умолчанию, определенное в ATLDB.H. Чтобы задать свойству нужное вам значение, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md). Чтобы установить `VARTYPE` и [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) для свойства в то же время, используйте [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md).

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_ex"></a><a name="property_info_entry_ex"></a>PROPERTY_INFO_ENTRY_EX

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID, vt, dwFlags, value, options)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

*vt*<br/>
[входные данные] `VARTYPE` этой записи свойства. (Определяется в wtypes.h)

*dwFlags*<br/>
[входные данные] Значение [DBPROPFLAGS](/previous-versions/windows/desktop/ms724342(v=vs.85)) , описывающее эту запись свойства.

*value*<br/>
[входные данные] Значение свойства с типом `DWORD`.

*Параметры*<br/>
DBPROPOPTIONS_REQUIRED или DBPROPOPTIONS_SETIFCHEAP. Как правило, поставщику не нужно устанавливать *опции,* так как он устанавливается потребителем.

#### <a name="remarks"></a>Remarks

С помощью этого макроса можно напрямую указать значение свойства типа `DWORD` , а также параметры и флаги. Чтобы задать свойству значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать свойству значение по своему усмотрению без параметров или флагов, используйте [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="property_info_entry_value"></a><a name="property_info_entry_value"></a>PROPERTY_INFO_ENTRY_VALUE

Представляет конкретное свойство в наборе свойств.

#### <a name="syntax"></a>Синтаксис

```cpp
PROPERTY_INFO_ENTRY_VALUE(dwPropID, value)
```

#### <a name="parameters"></a>Параметры

*dwPropID*<br/>
[входные данные] Значение [DBPROPID](/previous-versions/windows/desktop/ms723882(v=vs.85)) , которое может использоваться вместе с GUID набора свойств для идентификации свойства.

*value*<br/>
[входные данные] Значение свойства с типом `DWORD`.

#### <a name="remarks"></a>Remarks

С помощью этого макроса можно `DWORD`напрямую указать значение свойства типа. Установить значение значения по умолчанию, определенное в ATLDB. H, используйте [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Чтобы установить значение, флаги и параметры свойства, используйте [PROPERTY_INFO_ENTRY_EX.](../../data/oledb/property-info-entry-ex.md)

#### <a name="example"></a>Пример

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

### <a name="begin_provider_column_map"></a><a name="begin_provider_column_map"></a>BEGIN_PROVIDER_COLUMN_MAP

Отметки начала записи на карте столбцов поставщика.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)
```

#### <a name="parameters"></a>Параметры

*theClass*<br/>
(в) Название класса, к которой принадлежит эта карта.

#### <a name="example"></a>Пример

Вот пример поставщика колонки карты:

[!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]

### <a name="end_provider_column_map"></a><a name="end_provider_column_map"></a>END_PROVIDER_COLUMN_MAP

Отметки конца записей на карте столбцов поставщика.

#### <a name="syntax"></a>Синтаксис

```cpp
END_PROVIDER_COLUMN_MAP()
```

#### <a name="example"></a>Пример

Смотрите [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry"></a><a name="provider_column_entry"></a>PROVIDER_COLUMN_ENTRY

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY (name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*Член*<br/>
(в) Переменная участника, `dataClass` соответствующая столбце.

### <a name="provider_column_entry_fixed"></a><a name="provider_column_entry_fixed"></a>PROVIDER_COLUMN_ENTRY_FIXED

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_FIXED(name, ordinal, dbtype, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*dbtype*<br/>
(в) Тип данных в [DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*Член*<br/>
(в) Переменная участника `dataClass` в том, что хранит данные.

#### <a name="remarks"></a>Remarks

Позволяет указать тип данных столбца.

#### <a name="example"></a>Пример

Смотрите [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_gn"></a><a name="provider_column_entry_gn"></a>PROVIDER_COLUMN_ENTRY_GN

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_GN (name, ordinal, flags, colSize, dbtype, precision, scale, guid)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*Флаги*<br/>
(в) Определяет способ возврата данных. Смотрите `dwFlags` описание в [DBBINDING структур](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*colSize*<br/>
(в) Размер столбца.

*dbtype*<br/>
(в) Указывает тип значения данных. Смотрите `wType` описание в [DBBINDING структур](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*Точность*<br/>
(в) Указывает точность использования при получении данных, если *dbType* DBTYPE_NUMERIC или DBTYPE_DECIMAL. Смотрите `bPrecision` описание в [DBBINDING структур](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*Масштаб*<br/>
(в) Указывает масштаб, который можно использовать при получении данных, если dbType DBTYPE_NUMERIC или DBTYPE_DECIMAL. Смотрите `bScale` описание в [DBBINDING структур](/previous-versions/windows/desktop/ms716845(v=vs.85)).

*Guid*<br/>
Схема rowset GUID. Смотрите в *справке программиста OLE DB* о схеме и их GUID-справочниках [с](/previous-versions/windows/desktop/ms713686(v=vs.85)) мною.

#### <a name="remarks"></a>Remarks

Позволяет указать размер столбца, тип данных, точность, масштаб и схему rowset GUID.

### <a name="provider_column_entry_length"></a><a name="provider_column_entry_length"></a>PROVIDER_COLUMN_ENTRY_LENGTH

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name, ordinal, size, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*Размер*<br/>
(в) Размер столбца в байтах.

*Член*<br/>
(в) Переменная участника `dataClass` в этом хранит данные столбца.

#### <a name="remarks"></a>Remarks

Позволяет указать размер столбца.

#### <a name="example"></a>Пример

Смотрите [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_str"></a><a name="provider_column_entry_str"></a>PROVIDER_COLUMN_ENTRY_STR

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_STR(name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*Член*<br/>
(в) Переменная участника в классе данных, которая хранит данные.

#### <a name="remarks"></a>Remarks

Используйте этот макрос, когда данные столбца считаются [DBTYPE_STR.](/previous-versions/windows/desktop/ms711251(v=vs.85))

#### <a name="example"></a>Пример

Смотрите [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).

### <a name="provider_column_entry_type_length"></a><a name="provider_column_entry_type_length"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name, ordinal, dbtype, size, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*dbtype*<br/>
(в) Тип данных в [DBTYPE](/previous-versions/windows/desktop/ms711251(v=vs.85)).

*Размер*<br/>
(в) Размер столбца в байтах.

*Член*<br/>
(в) Переменная участника в классе данных, которая хранит данные.

#### <a name="remarks"></a>Remarks

Как и [PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md) но также позволяет указать тип данных столбца, а также размер.

### <a name="provider_column_entry_wstr"></a><a name="provider_column_entry_wstr"></a>PROVIDER_COLUMN_ENTRY_WSTR

Представляет определенный столбец, поддерживаемый поставщиком.

#### <a name="syntax"></a>Синтаксис

```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name, ordinal, member)
```

#### <a name="parameters"></a>Параметры

*name*<br/>
(в) Название столбца.

*Порядковый*<br/>
(в) Номер столбца. Если столбец не является столбцей закладки, номер столбца не должен быть 0.

*Член*<br/>
(в) Переменная участника в классе данных, которая хранит данные.

#### <a name="remarks"></a>Remarks

Используйте этот макрос, когда данные столбца являются нулевым истечением строки символов Unicode, [DBTYPE_WSTR.](/previous-versions/windows/desktop/ms711251(v=vs.85))

### <a name="begin_schema_map"></a><a name="begin_schema_map"></a>BEGIN_SCHEMA_MAP

Обозначает начало карты схемы.

#### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_SCHEMA_MAP(SchemaClass);
```

#### <a name="parameters"></a>Параметры

*СхемаКласс*<br/>
Класс, содержащий MAP. Обычно это будет класс сеанса.

#### <a name="remarks"></a>Remarks

Подробнее о строках схем ы [idBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) см.

### <a name="end_schema_map"></a><a name="end_schema_map"></a>END_SCHEMA_MAP

Обозначает конец карты схемы.

#### <a name="syntax"></a>Синтаксис

```cpp
END_SCHEMA_MAP()
```

#### <a name="remarks"></a>Remarks

Для получения дополнительной [IDBSchemaRowsetImpl Class](../../data/oledb/idbschemarowsetimpl-class.md)информации см.

### <a name="schema_entry"></a><a name="schema_entry"></a>SCHEMA_ENTRY

Ассоциирует GUID с классом.

#### <a name="syntax"></a>Синтаксис

```cpp
SCHEMA_ENTRY(guid,
   rowsetClass);
```

#### <a name="parameters"></a>Параметры

*Guid*<br/>
Схема rowset GUID. Смотрите в *справке программиста OLE DB* о схеме и их GUID-справочниках [с](/previous-versions/windows/desktop/ms713686(v=vs.85)) мною.

*rowsetClass*<br/>
Класс, который будет создан для представления строки схемы.

#### <a name="remarks"></a>Remarks

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) может запросить карту для списка GUID, или он может создать ряд, если он получил GUID. Создается схема `IDBSchemaRowsetImpl` строки, аналогичная `CRowsetImpl`классу, полученному из стандарта, за исключением того, что он должен предоставить метод, который имеет следующую `Execute` подпись:

```cpp
HRESULT Execute (LONG* pcRowsAffected,
    ULONG cRestrictions,
    const VARIANT* rgRestrictions);
```

Эта `Execute` функция заполняет данные rowset. AtL Project Wizard создает, как описано в [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в *справке программиста OLE DB,* три начальные схемы строк в проекте для каждой из трех обязательных схем OLE DB:

- DBSCHEMA_TABLES

- DBSCHEMA_COLUMNS

- DBSCHEMA_PROVIDER_TYPES

Мастер также добавляет три соответствующие записи на карте схемы. Дополнительную информацию об использовании мастера для создания поставщика можно просмотреть для [создания поставщика.](../../data/oledb/creating-an-ole-db-provider.md)

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
[Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Макрос для шаблонов поставщика УСЛУГ OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)
